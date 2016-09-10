---
layout: post
title:  "Survey-Rails Project"
date:   2015-08-12 9:25:5
---

I planned to write this post yesterday, but getting my wisdom teeth out hurt a lot more than I expected.

Anyways, I have been working on this project for the past couple of weeks and I think I have gotten it to a point that I am happy with.

Check out the [github] and [survey-rails] test site.

This was a good project to work on because it involved many models working togethere and also included heavy ajax which was something I needed to learn. In this website, a user can log in or create an account. From there, they can create surveys, take surveys, and see the stats of the results of their surveys. 

<h3> What I learned: </h3>

<ol>
	<li>
		 One of the most important bits of information I learned was that by adding 
		{% highlight ruby %}
		 remote: true
		{% endhighlight %}
		to my forms, it would automatically submit via ajax. This saved me time from having to write the ajax for each submit.
	</li>
	<br>
	<li>
		After making my own flash messages on the last project, I experimented with toastr messages which are a lot cleaner and look nicer than the ones I was making.
	</li>
	<br>

	<li>
		By using 6 models in the website, it forced me to think about how each model was interacting and how I could connect them. 
	</li>
	<br>

	<li>
		I also experimented with foundation icons (which don't seem to work all the time on the test site, but do locally). They added a nice touch to the site and make it easier to navigate.
	</li>
	<br>

	<li>
		I added a bar graph and pie graph in the stats section for each question on the survey. I used google charts which worked very well. This also was good practice for displaying data, which my next project will be on.
	</li>
	<br>

	<li>
		On my route to understanding how jquery and ajax work, I had to learn more about js.erb files and how rendering works.
		{% highlight ruby %}
		 format.js {render :file => "/questions/update.js.erb" , content_type: 'text/javascript', :locals => {:question => @question, :choice => Choice.new} }
		{% endhighlight %}
		before doing this project, I had no idea what the render block was for but after researching it, I found the purpose. It finds the type of request being sent and matches the type to the correct response. This was useful in this project because it allowed me to give error and success messages along with updating the page.
	</li>
	<br>
	<li>
		One major thing I learned during the project was performance testing. I used both a website called loader.io where I did load testing on getting pages, along side with benchmarking to test post routes.
		I wrote this <a href="https://github.com/drewburns/survey_rails/blob/master/test/performance/surveys_test.rb"> test page </a> which along with fixtures to test how fast the server could respond to mulitple requests.

		{% highlight ruby%}
		# rake test:benchmark
		SurveysTest#test_index (1.45 sec warmup)
		           wall_time: 5 ms
		              memory: unsupported
		             objects: unsupported
		             gc_runs: 0
		             gc_time: 0 ms
		.SurveysTest#test_submit_survey (1.64 sec warmup)
		# ran this test 350 times
		           wall_time: 1.54 sec
		              memory: unsupported
		             objects: unsupported
		             gc_runs: 3
		             gc_time: 105 ms
		.SurveysTest#test_show (7 ms warmup)
		           wall_time: 6 ms
		              memory: unsupported
		             objects: unsupported
		             gc_runs: 0
		             gc_time: 0 ms
		{% endhighlight%}
		It also created a file to view the records in which I could use to visualize the results of the test.

		From the loader.io test, which tested the process of getting the survey:
		<img src="https://i.gyazo.com/cbff3ee5677b71ed683941ccb1bca372.png">
		This result was longer than the test I ran with benchmark but it was on heroku which is slower than the local environment.
	</li>
	<br>
</ol>


<h3> What I want to learn: </h3>

<ol>
	<li>
		 Even though the ajax worked well most of the time, there were still on rare occasion times when it wouldn't do what I was expecting it to. I want to become better at ajax and jquery so I can make my projects as easy to use as possible.
	</li>
	<br>
	<li>
		 I also want to learn more about the asset pipeline because I have a feeling that is the reason why the icons aren't working in production.
	</li>
	<br>
</ol>

<h3> Feedback from testing: </h3>
<p>I had few people test the site and got their feedback. For tech savy people like my friend and my brother, there was no issues at all really with the site. But for less inclined people like my mother, there was a bit more of an issue. For the next project, I will have to find a balance bewteen making the site fool proof and not overdoing it with instructions. Most of the issue for the non tech savvy people came with creating the survey form. I though about changing the form to make it easier to use but after looking at the edit form at SurveyMonkey, I decided mine was actually better. Although theirs has more options, mine is simpler to use.
<br><br>
The survey monkey edit page:
<img src="https://i.gyazo.com/36d8c27eb459d2dc9d365c59a19b51b1.png">
</p>


[github]:      https://github.com/drewburns/survey_rails
[survey-rails]: https://survey-rails.herokuapp.com

