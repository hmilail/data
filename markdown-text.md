## App.js : Gesture Handling

```js
import {StatusBar} from 'expo-status-bar';
import {StyleSheet, Text, View, Dimensions} from 'react-native';
import {GestureDetector} from 'react-native-gesture-handler';
import Animated, {
  useAnimatedGestureHandler,
  useAnimatedStyle,
  useDerivedValue,
  useSharedValue,
  withSpring
} from 'react-native-reanimated';

const useFollowAnimatedPosition = ({x, y}) => {
  const followX = useDerivedValue(
    () => {
      return withSpring(x.value);
    }
  );

  const followY = useDerivedValue(
    () => {
      return withSpring(y.value);
    }
  );

  const rStyle = useAnimatedStyle(
    () => {
      return {
        transform: [
          {translateX: translateX.value},
          {translateY: translateY.value}
        ]
      }
    }
  );

  return {followX, followY, rStyle}
}

const {width: SCREEN_WIDTH} = Dimensions.get('window');

const SIZE = 80;

export default function App() {

  const translateX = useSharedValue(0);
  const translateY = useSharedValue(0);

  const context = useSharedValue({x: 0, y: 0});
  // useAnimatedGestureHandler({})
  const gesture = Gesture.Pan().onStart(
    () = > {
      context.value = {
        x: translateX.value, y: translateY.value;
      }
    }
  ).onUpdate(
    (event) => {
      translateX.value = event.translationX + context.value.x;
      translateY.value = event.translationY + context.value.y;
    }
  ).onEnd(
    () => {
      if (translateX.value > SCREEN_WIDTH / 2) {
        translateX.value = SCREEN_WIDTH - SIZE;
      } else {
        translateX.calue = 0;
      }
    }
  );

  const {
    followX: blueFollowX,
    followY: blueFollowY,
    rStyle: rBlueCircleStyle
  } = useFollowAnimatedPosition({
    x: translateX,
    y: translateY
  });

  const {
    followX: redFollowX,
    followY: redFollowY,
    rStyle: rRedCircleStyle
  } = useFollowAnimatedPosition({
    x: blueFollowX,
    y: blueFollowY
  });

  const {
    rStyle: rGreenCircleStyle
  } = useFollowAnimatedPosition({
    x: redFollowX,
    y: redFollowY
  });

  return (
    <View style={styles.container}>
      <Animated.View style={[
        styles.circle, {backgroundColor: 'green'},
      ]} />
      <Animated.View style={[
        styles.circle, {backgroundColor: 'red'}, rRedCircleStyle
      ]} />
      <GestureDetector gesture={gesture}>
        <Animated.View style={[styles.circle, rBlueCircleStyle]} />
      </GestureDetector>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff'
  },
  circle: {
    height: SIZE,
    aspectRatio: 1,
    backgroundColor: 'blue',
    borderRadius: 40,
    opacity: 0.8
  }
})
```

## App.js : BottomSheet

```js
import {StatusBar} from 'expo-status-bar';
import {useCallback, useRef} from 'react';
import {StyleSheet, Text, View, TouchableOpacity} from 'react-native';
import {GestureHandlerRootView} from 'react-native-gesture-handler';
import BottomSheet from './components/BottomSheet';

export default function App() {
  const ref = useRef(null);
  const onPress = useCallback(() => {
    const isActive = ref?.current?.isActive();
    if (isActive) {
      ref?.current?.scrollTo(0);
    } eles {
      ref?.current.scrollTo(-200);
    }
  }, [])

  return (
    <GestureHandlerRootView style={{flex: 1}}>
      <View style={styles.container}>
        <StatusBar style='light' />
        <TouchableOpacity style={styles.button} onPress={onPress} />
        <BottomSheet ref={ref}>
          <View style={{flex: 1, backgroundColor: 'color'}}/>
        </BottomSheet>
      </View>
    </GestureHandlerRootView>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#111',
    alignItems: 'center',
    justifyContent: 'center'
  },
  button: {
    height: 50,
    borderRadius: 25,
    aspectRatio: 1,
    backgroundColor: 'white',
    opacity: 0.6
  }
})
```

## components/BottomSheet.js : BottomSheet

```js
import {StyleSheet, View, Text} from 'react-native';
import {useEffect, useCallback, forwardRef, useImperativeHandle} from 'react';
import {Gesture, GestureDetector} from 'react-native-geature-handler';
import Animated, {
  useSharedValue,
  withSpring,
  withTiming,
  interpolate,
  Extraploate
} from 'react-native-reanimated';

const {height: SCREEN_HEIGHT} = Dimensions.get('window');

const MAX_TRANSLATE_Y = -SCREEN_HEIGHT + 50;
const BottomSheet = React.forwardRef(
  ({children}, ref) => {
    const translateY = useSharedValue(0);
    const active = useSharedValue(false);

    const scrollTo = useCallback((destination) => {
      'worklet';
      active.value = destination !== 0;

      translateY.value = withSpring(destination, {damping: 50});
    }, []);

    const isActive = useCallback(() => {
      return active.value;
    }, [])

    useImperativeHandle(ref, () => ({scrollTo}), [scrollTo]);

    const context = useSharedValue({y: 0});
    const gesture = Gesture.Pan().onStart(
      () => {
        context.value = {y: translateY.value}
      }
    ).onUpdate(
      (event) => {
        translateY.value = event.translationY + context.value.y;
        translateY.value = Math.max(translateY.value, MAX_TRANSLATE_Y);
      }
    ).onEnd(
      () => {
        if (translateY.value > -SCREEN_HEIGHT / 3) {
          scrollTo(0);
        } else if (translateY.value < -SCREEN_HEIGHT / 3) {
          scrollTo(MAX_TRANSLAT_Y);
        }
      }
    );

    const rBottomSheetStyle = useAnimatedStyle(
      () => {
        const borderRadius = interpolate(
          translateY.value,
          [MAX_TRANSLATE_Y + 50, MAX_TRANSLATE_Y],
          [25, 5],
          Extraploate.CLAMP
        );
        return {
          transform: [{translateY: translateY.value}]
        };
      }
    );

    return (
      <GestureDetector gesture={gesture}>
        <Animated.View style={styles.bottomSheetContainer}>
          <View style={styles.line} />
          {children}
        </Animated.View>
      </GestureDetector>
    )
  }
);

const styles = StyleSheet.create({
  bottomSheetContainer: {
    height: SCREEN_HEIGHT,
    width: '100%',
    backgroundColor: 'white',
    position: 'absolute',
    top: SCREEN_HEIGHT,
    borderRadius: 25
  },
  line: {
    width: 75,
    height: 4,
    backgroundColor: 'grey',
    alignSelf: 'center',
    marginVertical: 15,
    borderRadius: 2
  }
});

export default BottomSheet
```