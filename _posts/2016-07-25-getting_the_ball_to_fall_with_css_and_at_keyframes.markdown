---
layout: post
title:  "Getting the Ball to {Fall} with CSS and @Keyframes"
date:   2016-07-25 22:45:26 +0000
---

I am nearing the end of the HTML/CSS portion of the Learn program, and so far it has been smooth sailling. More often than not, I find myself exploring beyond the lessons within the Learn program, reading blogs, browsing Github, or messing around in <a href="http://jsfiddle.net" target="_blank">jsfiddle</a> and <a href="http://codepen.io" target="_blank">codepen</a>. I'm planning on posting more frequently with my favorite concepts / mini-projects.

**@Keyframes is your friend**

My introduction to the css @keyframes rule was about a year ago when I was working through <a href="http://codeacademy.com" target="_blank">Code Academy</a>, and I gave up on it almost immediately. It looked like a whole lotta code, just to make the simplest animation. Turns out, it's WAYYY easier than I first thought. 

**Make the ball fall**

One of my recent for-fun animation demos is a row of circles falling up and down infinitely. Let's take a look!

**First, the `<div>` ball**

**HTML**

```
<div class="ball">
```

**CSS**

```
.ball {
  height: 50px;
  width: 50px;
  border-radius: 100px;
  display: inline-block;
  background: blue;
}
```

**Creating @keyframes animation**

@keyframes are easy enough to work with for starters. First, we'll create the animation itself.

We call the @keyframes rule, name it, then fill our timing selectors with CSS styling. The basic syntax looks like this:

```
@keyframes [animation-name] {
 /* start of animation */ 0% {
    //CSS style
  }
  
 /* end of animation */ 100% {
   //CSS style 
  }
}
```

You can include as many points within the animation duration as you wish, so long as they are between 0% and 100%.

**Fall Animation**

```
@keyframes fall {
  0% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(150px);
  }
  100% {
    transform: translateY(0px);
  }
}
```

*In short, the code is saying this:*

0%: Element starting position

50%: Element is pushed down by 150 pixels;

100%; Element flies back up to it's starting position

Browser support is pretty easy. Just create your @keyframes animation, then copy/paste three times. Then, you add three prefixes to the @keyframes, after the '@' and before 'keyframes,' like so:

standard syntax: @keyframes [animation name] { ...animation code...}

chrome/safari support: @-webkit-keyframes [animation name] { ...animation code...}

firefox support: @-moz-keyframes [animation name] { ...animation code...}

opera support: @-o-keyframes [animation name] { ...animation code...}

**Targeting the animation in CSS**

Now we have our @keyframes animation, but the ball isn't going to do anything! We have to target the animation in CSS with the 'animation' property. The best way to do this is by creating a class with a name similar to the animation, then assigning the class to the target element. The animation property is actually a shorthand for eight other properties, but we will just worry about three: animation-name, animation-duration, and animation-iteration-count. 

Here is an example:

**CSS animation**

```
.fall {
  animation: fall 2s infinite;
}
```

Again, for browser support, you can add the prefixes:

```
.fall {
  -webkit-animation: fall 2s infinite;
  -moz-animation: fall 2s infinite;
  -o-animation: fall 2s infinite;
  animation: fall 2s infinite;
}
```

Here's the breakdown of this animation property shorthand:

animation: fall 2s infinite; 

is the same as

animation-name: fall //links to the @keyframes animation with the same name

animation-duration: 2s // how long the animation will last, can also be set in milliseconds (ms).

animation-iteration-count: infinite // how many times to play the animation

**Last but not least**

We give the .fall class to the .ball div, and that's it!

```
<div class="ball fall">
```

**Completed Code**

**HTML**

```
  <div>
    <div class="ball fall">
  </div>
```

**CSS**

```
div {
  text-align: center;
}

.ball {
  height: 50px;
  width: 50px;
  border-radius: 100px;
  display: inline-block;
  background: blue;
}

.fall {
  animation: fall 2s infinite;
}

@keyframes fall {
  0% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(150px);
  }
  100% {
    transform: translateY(0px);
  }
}

@-webkit-keyframes fall {
  0% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(150px);
  }
  100% {
    transform: translateY(0px);
  }
}

@-moz-keyframes fall {
  0% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(150px);
  }
  100% {
    transform: translateY(0px);
  }
}

```

The extra div is just to center the ball in the page.

Here is the <a href="http://codepen.io/BeejLuig/details/NArJAw/" target="_blank">result</a>. Play around with it!

<p data-height="355" data-theme-id="0" data-slug-hash="NArJAw" data-default-tab="css,result" data-user="BeejLuig" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/BeejLuig/pen/NArJAw/">NArJAw</a> by BJ Cantlupe (<a href="http://codepen.io/BeejLuig">@BeejLuig</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

As a bonus, here is what my <a href="http://codepen.io/BeejLuig/pen/XKqOQP" target="_blank">final fiddle</a> looks like. It adds some new concepts, but they might have to wait for another post...

<p data-height="305" data-theme-id="0" data-slug-hash="XKqOQP" data-default-tab="css,result" data-user="BeejLuig" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/BeejLuig/pen/XKqOQP/">XKqOQP</a> by BJ Cantlupe (<a href="http://codepen.io/BeejLuig">@BeejLuig</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>




