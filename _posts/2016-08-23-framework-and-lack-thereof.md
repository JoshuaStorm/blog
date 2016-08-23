---
layout: post
title:  "JavaScript: Framework or the Lack Thereof"
date:   2016-08-23 12:50:46 -0400
categories: jekyll update
---
_Note: this blog is that of a student. Although I hope to provide a unique perspective, I do not claim to be an authoritative expert on the subjects discussed._

Creating my first web app has made me ask the question a few too many times:
what framework should I use? Should I even use a framework?

Perhaps my specific use case makes this question particularly difficult, but
I feel like this is a major difficulty for new developers, particularly when it
comes to JavaScript.

### Do I want to use a framework for my project?

Does _this_ project _need_ a framework? No. Would this project be _easier_ to implement with a framework? Perhaps - and this is where the question becomes difficult.

When trying to make this decision for myself, I figured there were two major advantages of a framework: templates and data-binding.

As far as templates go, they would not meet my needs. My project - a subtractive synthesizer built into a single responsive webpage - does not well conform to the usual web templates.

Data-binding is a bit trickier. Using `p5.js` to build WebSynth allows me the p5.dom library which allows for easy creation and placing of DOM sliders and buttons, but screen scaling has proven to be a fairly difficult task. Just to give you an idea, this is how I am currently handling dynamic page size with my synthesizers plethora of sliders:

{% highlight javascript %}
function setupSliders() {
  var xTranslateKeys = width / 2;
  var yTranslateKeys = height / 2;
  var sliderHeight = height / 8;
  var sliderSpacer = width / 30;
  var xTranslateSliders = width / 72;

  // Octave slider
  octaveSlider = setupSlider(xTranslateSliders + (19 * sliderSpacer), 3.5 * sliderHeight, 4, 2);
  setupSliderLabel(xTranslateSliders + (19 * sliderSpacer), 3.5 * sliderHeight, 'Octave', false);
  // Tons more slider definitions continue ad nauseam...
}
{% endhighlight %}

As you can see, this is not exactly the cleanest way of doing things... But does this justify dropping my project into a framework? A framework which would likely require me to completely change my current data-binding architecture?

Even this is an overly simplified way of looking at JS frameworks. Go ahead and google "why/why not use a javascript framework" and you'll see what is being thrown at a new JS dev: a lot of conflicting information. True, the answer is subjective at the end of the day, but even with that in mind, I find myself struggling to answer the question for my project alone.

### Does a framework offer functionality that can't be easily implemented in my project?

I decided to push off answering the "should I" question altogether and just to look into the frameworks available and try to see if they offer something I feel I am missing:

I could very quickly cut out a lot of the big ones knowing that this project would live and die as a single page application. However, even scouring through `Durandal`, `Angular`, and a few other framework's examples, tutorials, and docs I cannot quite seem to find what I am looking for.

Perhaps, my issue is not with frameworks. Perhaps, my issue is I want an easy solution for a problem I need to solve elsewhere in the web dev trifecta. Maybe hopping onto a framework won't solve my problem, but a better understanding of CSS would.

In the end, all I need is some well placed sliders and knobs.

### Other difficulties with frameworks

Regardless of the end decision for my WebSynth project, there still exists a very real difficulty for new (and perhaps even experienced) developers. Choosing a framework isn't easy, and it definitely isn't made easier by all the misinformation out there.

Not to call anyone out in particular, but in my research, I found many lists of "JavaScript Frameworks you NEED TO KNOW IN 2016" that contained `Node.js` and `jQuery`. Who knows what other inaccuracies there are in some of these lists that I am not aware of just because I am personally unaware.
