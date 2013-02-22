AlphaScroll
=======================

An indexed scrollbar plugin for jQuery Mobile
___

AlphaScroll adds an alphabetized scrolling widget to jQuery Mobile listviews that contain autodividers. The widget addresses the difficulty of quickly scrolling large lists on small mobile device screens.

A [working demo](http://www.designkode.com/demos/alphascroll/) is available and you can read a bit more about this project [here](http://www.designkode.com/blog/alphascroll-jquery-mobile).

##Uses

AlphaScroll is for use on jQuery Mobile listviews that are alphabetically sorted and include autodividers: `data-autodividers="true"`.

AlphaScroll responds to orientation change events to display a shortened list of letters when in landscape mode or when the screen has a height of less than 320 pixels.

##Setup

First, include the AlphaScroll CSS and JavaScript files in your HTML:

```html
<link rel="stylesheet" type="text/css" href="css/jquery.mobile.alphascroll.css" />
<script type="text/javascript" src="js/jquery.mobile.alphascroll.js"></script>
```

Create your listview as you normally would. In the demo, I take an array of names, sort it and then after looping through the array to build a set of `<li>` list items, append the list items to an unordered list that has its data-autodividers attribute set to true:

```html
<ul id="mylistview" data-role="listview" data-autodividers="true"></ul>
```

For dynamically generated lists, you would then call refresh to apply the jqMobile styles and finally call alphascroll on the listview to generate the alphabet scroller. The refresh and alphascroll() calls can be chained together:

```javascript
$( '#mylistview' ).listview( 'refresh' ).alphascroll();
```

or called seperately:

```javascript
$( '#mylistview' ).listview( 'refresh' );
$( '#mylistview' ).alphascroll();
```

For hard-coded lists that don't require a refresh, you can simply attach the alphascroll method to your listview:

```javascript
$( '#mylistview' ).alphascroll();
```

##Customization

The AlphaScroll plugin in its current state doesn't take any options. You may alter the look and placement of the scroll widget by editing the CSS in jquery.mobile.alphascroll.css.

##Caveats

By default, jQuery Mobile's listviews attach an arrow icon on the right side of each list item. These icons fall directly below the alphascroll widget, which can look a little funny. You can either remove the arrow icons by setting data-icon="false" on each list item (as in the demo), or provide a solid background color to the .alphascroll and .alphascroll:active selectors in the CSS.

Testing on an iPhone 5, scrolling rapidly back and forth on the alphascroll widget can cause some screen flashing. This doesn't seem to happen on desktop browsers and is likely due to the slower processor speed of mobile devices.