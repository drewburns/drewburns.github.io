---
layout: post
title:  "Css Animations"
date:   2015-08-24 16:47:20
---
Link to the [Github] Page<br>
I decided to take a break from Rails over the past week and learn about CSS animations.
I have used the library called Animate.css for some of my projects, but I wanted to learn how to make my own animations.
I learned there are a few components to make an item come to life. First you need the object that the animation will be used on.
{% highlight html %}
 <div class="sun"></div>
{% endhighlight %}
Then you need to make the animation that will be used. This is done by making a keyframes sequence and applying it to that item.
{% highlight css %}
 @keyframes sun-pattern {
	0% {
		background-color: gold;
	}
	50% {
		transform: translate(0,600px);
		background-color: #FE5B35;
	}
	100% {
		background-color: #FEFCD7;
	}
}
.sun {
	animation: sun-pattern 20s 3s infinite alternate;
}
{% endhighlight %}

Now this animation will continue forever, taking 20 seconds to complete. It will also have a 3 second buffer time and when the animation finishes, it will go again except backwards.

I also experimented a little bit with svg, or scalable vector graphics. I wanted a cloud shape for my animation but didn't want to go looking for images to use. I ended up using a code snippet I found online for a cloud shape. After reading more about svg, I learned that it is a way of using a grid system to draw lines and make shapes that can be easily scaled.
{% highlight html %}
<svg class="cloud-1" viewBox='0 0 105 105'>
  <path d='M 25,60 
           a 20,20 1 0,0 0,40 
           h 50 
           a 20,20 1 0,0 0,-40 
           a 10,10 1 0,0 -15,-10 
           a 15,15 1 0,0 -35,10  
           z' />
</svg>
{% endhighlight %}

[github]: https://github.com/drewburns/css_animations