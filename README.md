jQuery Progress Tracker
======================

A small (2KB) jQuery plugin that creates a fixed progress indicator based on your content and allows linking between them.

---

## Options

**linking** - _default:_ **_true_**  
When set to true, clicking on a bullet will animate to the top of that section on the page

**tooltip** - _default:_ **_“constant”_**  
This determines when the tooltip for a bullet should be shown. There are 2 options:  
+ “constant” - The active tooltip is always shown, and change as you move between sections. No other tooltip is visible at any point.  
+ “hover” - As standard all tooltips are hidden, but when you hover a bullet, the tooltip for that one appears.

**positiveTolerance** - _default:_ **_0_**  
Integer - The number specified is added to the default value at which the tracker changes to the next section. For example, if the next section started at 200px, and a positiveTolerance of 50 was specified, the tracker would not switch to the next section at 250px.

**negativeTolerance** - _default:_ **_0_**  
Integer - The number specified is subtracted from the default value at which the tracker changes to the next section. For example, if the next section started at 200px, and a negativeTolerance of 50 was specified, the tracker would not switch to the next section at 150px.

**displayWhenActive** - _default:_ **_true_**  
Only displays the progress tracker when the user is between the top of the first section and the bottom of the last; essentially, it is only shown when the tracker sections are in view. Specify false if you want the tracker to always show.

**disableBelow** - _default:_ **_0_**  
Integer - Specify the value (in pixels) that you wish the progress tracker to be hidden when it is below that.

**tracking** - _default:_ **_“tracker”_**  
Specifies what the plugin takes into account when deciding when to switch to the next section.  
+ “tracker” - With this specified, the tracker will switch to the next section when the top of the tracker element is in line or below the threshold of that section (the demo has this behaviour)  
+ “viewport” - Instead of being based on the top offset of the tracker, this option switches the tracker’s active section when that section reaches the top of the viewport (window)

---

## Setup

1. Include jQuery followed by progressTracker.js just before the end of the body tag  
```html
<script src="http://code.jquery.com/jquery-latest.min.js"></script>
<script src="jquery.progresstracker.min.js"></script>
```  
2. Include the Progress Tracker CSS in the head  
```html
<link rel="stylesheet" type="text/css" href="static/css/jquery.progresstracker.css">
```  
3. Initialise the plugin below the included scripts  
```javascript
<script>
	(function() {
		//Standard initialisation
		$('body').progressTracker();
	})();
</script>
```  
Or with custom options:  
```javascript
<script>
	(function() {
		$('body').progressTracker({
	        linking : true,
	        tooltip : "constant",
	        negativeTolerance : 0,
	        positiveTolerance : 0,
	        displayWhenActive : true,
	        disableBelow : 600
	    });
	})();
</script>
```  
4. In order for the plugin to pick up all the relevant sections, you must add the class of `pt-section` to it. You must also specify a `data-name` to be the content of the tooltip, and an `id` if you intend to use deeplinking when you click on a bullet.  
```html
<div class="pt-section" data-name="Sec One" id="ptsection-one"></div>
```  

---

## Demo  

[Live demo can be found here](http://mrfirthy.me/experiments/example/jquery-progress-tracker/) using the same code as the repository

---

## Questions  

If you find anything wrong with the plugin, have issues getting it working, or think of something cool it could do, feel free to submit an issue.
