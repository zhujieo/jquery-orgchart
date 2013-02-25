jquery-orgchart
===============

JQuery Organisation Chart Plugin

This is a small JQuery plugin that generates a hierarchical orginisational chart from a nested unordered list.

HTML/CSS purists likely would not be happy with this since it uses nested tables to achieve the layout. Nevertheless, it works pretty well and you can make nice looking interactive organisational charts with it quite easily.

This has been tested on Firefox and Chrome on Linux.

Features
--------

 * HTML markup, including clickable hyperlinks, inside the chart nodes;
 * All attributes from the source list get baked into the corresponding chart nodes (e.g. you can annotate the nodes with your own "data" attributes);
 * Options to limit the chart to the desired number of levels, and show remaining levels in a single stack;
 * Optional callback to handle clicked chart nodes;
 * Small size, only 3K minified (6K un-minified);
 * Easy to to change the appearance of the chart by overriding a small number of CSS style rules;
 * Does exactly what it says on the tin, no feature bloat!
 
Configuration Options
---------------------

`chartClass` (string) is used to specify a CSS class to add to the created chart.

`container` (jQuery element) specifies the element that will contain the chart.

`depth` (integer) is used in conjunction with `stack` to configure at what level the stacking takes effect.

`fade` (boolean) is used to enable a fading animation when showing/hiding chart nodes.

`hoverClass` (string) is used to specify the CSS class that gets dynamically added to chart nodes on mouse-over.

`interactive` (boolean) is used to enable interactive chart features, like clicking to show/hide child nodes.

`levels` (integer) specifies how many levels deep in the source list are used to create the chart.

`nodeClicked` (function) callback function invoked when a chart node is clicked.

`nodeText` (function) callback function used to extract node text context.

`showLevels` (integer) specifies how many chart levels to show initially.

`speed` (jQuery speed) specifies the animation speed if `fade` is enabled.

`stack` (boolean) is used to enable stacking.
 
Simple Example
--------------

![Organisation Chart Demo](https://github.com/caprica/jquery-orgchart/raw/master/demo/simple.png "Simple Demo")

```
$("#organisation").orgChart({container: $("#main")});
```

In this example "#organisation" is the selector for the source list and the "container" option specifies the target container for the generated chart.

[Live Demo](http://capricasoftware.co.uk/jquery/neworgchart/demo/simple.html)

[Source for Simple Demo](https://github.com/caprica/jquery-orgchart/blob/master/demo/simple.html)

Simple Stacking Example
-----------------------

![Organisation Chart Stacking Demo](https://github.com/caprica/jquery-orgchart/raw/master/demo/simple-stacking.png "Simple Stacking Demo")

```
$("#organisation").orgChart({container: $("#main"), stack: true, depth: 2});
```

Building on the previous example, the "stack" option is added with a corresponding chart "depth" of "2". This means that the chart will display two levels before stacking any remaining levels in a single list.

[Live Demo]([Live Demo](http://capricasoftware.co.uk/jquery/neworgchart/demo/simple-stacking.html)

[Source for Simple Stacking Demo](https://github.com/caprica/jquery-orgchart/blob/master/demo/simple-stacking.html)

Styling Levels Example
----------------------

![Organisation Chart Styling Levels Demo](https://github.com/caprica/jquery-orgchart/raw/master/demo/styling-levels.png "Styling Levels Demo")

```
$("#organisation").orgChart({container: $("#main")});
```

```
div.orgChart div.node.level1 {
    background-color: #fbcece;
}
div.orgChart div.node.level1.special {
    background-color: white;
}
div.orgChart div.node.level2 {
    background-color: #cefbce;
}
div.orgChart div.node.level3 {
    background-color: #e0cefb;
}
```

Each node in the chart automatically gets assigned a class for its level, this can be used to style each level individually.

Any classes that are specified on items in the source list get applied to the corresponding chart node, this can also be used to customise the style for a particular node or collection of nodes. In this example the main protagonist has his own unique background colour applied, overriding the colour for his level in the chart. The root of the chart has level zero.

[Live Demo](http://capricasoftware.co.uk/jquery/neworgchart/demo/styling-levels.html)

[Source for Styling Levels Demo](https://github.com/caprica/jquery-orgchart/blob/master/demo/styling-levels.html)

Eating Your Own Dog Food Example
--------------------------------

![Organisation Chart Dog Food Demo](https://github.com/caprica/jquery-orgchart/raw/master/demo/dogfood.png "Dog Food Demo")

```
$("#organisation").orgChart({container: $("#main")});
```

[Live Demo](http://capricasoftware.co.uk/jquery/neworgchart/demo/dogfood.html)

[Source for Dog Food Demo](https://github.com/caprica/jquery-orgchart/blob/master/demo/dogfood.html)

Other Examples
--------------

[Simple Interactive Live Demo](http://capricasoftware.co.uk/jquery/neworgchart/demo/simple-interactive.html)  
[Links Live Demo](http://capricasoftware.co.uk/jquery/neworgchart/demo/links.html)  
[On-Click Live Demo](http://capricasoftware.co.uk/jquery/neworgchart/demo/onclick.html)
