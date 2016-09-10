---
layout: single
title:  "Recipe App"
date:   2015-12-22 9:25:5
---
Blog posts are like buses.
You wait forever for one, and then two come.

The Github: [github]

The Recipe App I created was in lieu of the Twitter app assignment by the Stanford Course. Some of their files were not compatable with the new Swift version, so I took it upon myself to make a similar project from stratch.

<h3>The App:</h3>
The app ran on the backend of the [GiveMeRecipes] rails site I made a while back. I had to reconfigure the store of the files of the images for the website using Cloudinary. It took a long time to figure out what I was doing, but after that I was able to upload images from the app and send them to the app through the custom API that needed to be made for the app.


The app allows users to log in and out using their accounts from the site.From there, the user can view all recipes, see specific user's recipes, or view a single recipe. Creating recipes from the app is also very easy.

<h3>What I learned</h3>
<ul>
	<h4>Swift</h4>
	<li>Scroll Views</li>
	<li>Autolayout</li>
	<li>HTTP Requests</li>
	<li>Closures/Completion Handlers</li>
	<li>Images</li>
	<li>Table Views</li>
	<li>HTTP Authentication</li>
	<h4>Rails</h4>
	<li>How to make API</li>
	<li>Image Storage</li>
	<li>HTTP Authentication</li>
</ul>

<h3>What I could add</h3>
I would like to add a sign up page and a search feature to look for recipes. I attempted to make a search feature in the app but I couldn't get it to work properly.



[GiveMeRecipes]: https://givemerecipes.herokuapp.com
[github]: https://github.com/drewburns/RecipeApp
