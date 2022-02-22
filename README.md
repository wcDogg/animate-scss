# animate.scss

A Sassy version of the much-loved [animate.css](https://github.com/daneden/animate.css). All the animations without the bloat <3

**[https://curlybracketdev.github.io/animate-scss/](https://curlybracketdev.github.io/animate-scss/)**

## Add to Workflow

1. Clone this repo to your `_sass` directory. 
2. Add `@import "animate/import";` to your Sass flow. 

## Enable A11y

`_animate-a11y` contains some common CSS resets related to animations. For this reason, it is commented out in `_import.scss`. If your theme does not already have these rules, you can uncooment this file to include them. 

## Enable Animations

The key idea behind **animate.sass** is to prevent bloat - why include thouseands of lines of unneeded CSS? Before you can use an animation, you must enable it in `_animate.scss`: 

```
$bounce: true;
$bounceIn: false;
$bounceInDown: false;
```

## HTML - Add a class for easy targeting

```
<div class="div--once"><p>once</p></div>
<div class="div--infinite"><p>infinite</p></div>
<div class="div--delay"><p>delay</p></div>
```

## Sass 

Animating an elment is super easy - just 2 lines in your Sass rules.

The base `@include` sets the animation's behavior and the `@exstend` specifies the animation to use. For reference, the source `@include` is: 

```
@include animate($duration: 300ms, $delay: false, $infinite: false) 
```

The base `@include` is already configured with defaults that are easy to adjust: 

* `duration` in milliseconds - default is `300ms`
* `delay` = `false` || `100ms` - default is `false`
* `infinite` = `false` || `true` - default is `false`

**EXAMPLE: Div bounces one time on hover**

```
.div--once {
    &:hover {
        @include animate(1000ms);
        @extend %rubberBand;
    }
}
```

**EXAMPLE: Div bounces continuosly on hover**

```
.div--infinite {
    &:hover {
        @include animate(1000ms, false, true);
        @extend %rubberBand;
    }
}

```
**EXAMPLE: Div bounce starts after a delay on hover**

```
.div--delay {
    &:hover {
        @include animate(1000ms, 1000ms, true);
        @extend %rubberBand;
    }
}
```
      
## @extend

```
@extend %bounce;
@extend %bounceIn;
@extend %bounceInDown;
@extend %bounceInLeft;
@extend %bounceInRight;
@extend %bounceInUp;

@extend %bounceOut;
@extend %bounceOutDown;
@extend %bounceOutLeft;
@extend %bounceOutRight;
@extend %bounceOutUp;

@extend %fadeIn;
@extend %fadeInDown;
@extend %fadeInDownBig;
@extend %fadeInLeft;
@extend %fadeInLeftBig;
@extend %fadeInRight;
@extend %fadeInRightBig;
@extend %fadeInUp;
@extend %fadeInUpBig;

@extend %fadeOut;
@extend %fadeOutDown;
@extend %fadeOutDownBig;
@extend %fadeOutLeft;
@extend %fadeOutLeftBig;
@extend %fadeOutRight;
@extend %fadeOutRightBig;
@extend %fadeOutUp;
@extend %fadeOutUpBig;

@extend %flash;

@extend %flipInX;
@extend %flipInY;
@extend %flipOutX;
@extend %flipOutY;

@extend %headShake;
@extend %heartBeat;
@extend %hinge;
@extend %jackInTheBox;
@extend %jello;

@extend %lightSpeedIn;
@extend %lightSpeedOut;

@extend %pulse;

@extend %rollIn;
@extend %rollOut;

@extend %rotateIn;
@extend %rotateInDownLeft;
@extend %rotateInDownRight;
@extend %rotateInUpLeft;
@extend %rotateInUpRight;

@extend %rotateOut;
@extend %rotateOutDownLeft;
@extend %rotateOutDownRight;
@extend %rotateOutUpLeft;
@extend %rotateOutUpRight;

@extend %rubberBand;

@extend %scaleInDown;
@extend %scaleOutUp;  

@extend %shake;

@extend %slideInDown;
@extend %slideInLeft;
@extend %slideInRight;
@extend %slideInUp;

@extend %slideOutDown;
@extend %slideOutLeft;
@extend %slideOutRight;
@extend %slideOutUp;

@extend %swing;
@extend %tada;
@extend %wobble;

@extend %zoomIn;
@extend %zoomInDown;
@extend %zoomInLeft;
@extend %zoomInRight;
@extend %zoomInUp;

@extend %zoomOut;
@extend %zoomOutDown;
@extend %zoomOutLeft;
@extend %zoomOutRight;
@extend %zoomOutUp;
```
