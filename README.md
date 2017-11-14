# com-zipwhip-widget-font2gcode
This widget lets you type text, render it into the 3D viewer, and then generate the gcode for the font. If you want to mill/laser/print text this is a great way to do it programmatically.

![alt text](screenshot.png "Screenshot")

## ChiliPeppr Widget / Font2Gcode

All ChiliPeppr widgets/elements are defined using cpdefine() which is a method
that mimics require.js. Each defined object must have a unique ID so it does
not conflict with other ChiliPeppr widgets.

| Item                  | Value           |
| -------------         | ------------- | 
| ID                    | com-zipwhip-widget-font2gcode |
| Name                  | Widget / Font2Gcode |
| Description           | This widget lets you type text, render it into the 3D viewer, and then generate the gcode for the font. If you want to mill/laser/print text this is a great way to do it programmatically. |
| chilipeppr.load() URL | http://raw.githubusercontent.com/chilipeppr/widget-font2gcode/master/auto-generated-widget.html |
| Edit URL              | http://ide.c9.io/chilipeppr/widget-font2gcode |
| Github URL            | http://github.com/chilipeppr/widget-font2gcode |
| Test URL              | https://preview.c9users.io/chilipeppr/widget-font2gcode/widget.html |

## Example Code for chilipeppr.load() Statement

You can use the code below as a starting point for instantiating this widget 
inside a workspace or from another widget. The key is that you need to load 
your widget inlined into a div so the DOM can parse your HTML, CSS, and 
Javascript. Then you use cprequire() to find your widget's Javascript and get 
back the instance of it.

```javascript
// Inject new div to contain widget or use an existing div with an ID
$("body").append('<' + 'div id="myDivComZipwhipWidgetFont2gcode"><' + '/div>');

chilipeppr.load(
  "#myDivComZipwhipWidgetFont2gcode",
  "http://raw.githubusercontent.com/chilipeppr/widget-font2gcode/master/auto-generated-widget.html",
  function() {
    // Callback after widget loaded into #myDivComZipwhipWidgetFont2gcode
    // Now use require.js to get reference to instantiated widget
    cprequire(
      ["inline:com-zipwhip-widget-font2gcode"], // the id you gave your widget
      function(myObjComZipwhipWidgetFont2gcode) {
        // Callback that is passed reference to the newly loaded widget
        console.log("Widget / Font2Gcode just got loaded.", myObjComZipwhipWidgetFont2gcode);
        myObjComZipwhipWidgetFont2gcode.init();
      }
    );
  }
);

```

## Publish

This widget/element publishes the following signals. These signals are owned by this widget/element and are published to all objects inside the ChiliPeppr environment that listen to them via the 
chilipeppr.subscribe(signal, callback) method. 
To better understand how ChiliPeppr's subscribe() method works see amplify.js's documentation at http://amplifyjs.com/api/pubsub/

  <table id="com-chilipeppr-elem-pubsubviewer-pub" class="table table-bordered table-striped">
      <thead>
          <tr>
              <th style="">Signal</th>
              <th style="">Description</th>
          </tr>
      </thead>
      <tbody>
      <tr><td colspan="2">(No signals defined in this widget/element)</td></tr>    
      </tbody>
  </table>

## Subscribe

This widget/element subscribes to the following signals. These signals are owned by this widget/element. Other objects inside the ChiliPeppr environment can publish to these signals via the chilipeppr.publish(signal, data) method. 
To better understand how ChiliPeppr's publish() method works see amplify.js's documentation at http://amplifyjs.com/api/pubsub/

  <table id="com-chilipeppr-elem-pubsubviewer-sub" class="table table-bordered table-striped">
      <thead>
          <tr>
              <th style="">Signal</th>
              <th style="">Description</th>
          </tr>
      </thead>
      <tbody>
      <tr valign="top"><td>/com-zipwhip-widget-font2gcode/getGcode</td><td>This is a powerful signal that you can send into this widget to ask
for Gcode from the widget for a font rendering. You can pass in all parameters you see in the UI
as options to this call. You should provide a callback method as well so this widget can call
back that method with the final Gcode based on the parameters you asked for.
<br>
Example:
<br>
Pass in {<br>
    callback: yourmethod, // the method we will callback with gcode string.<br>
    text: "my text", // the text you want rendered<br>
    size: 10, // float. size as height in mm. defaults to 10.<br>
    fontName: "helvetiker", // helvetiker, optimer, gentilis, droid/droid_sans, droid/droid_serif. defaults to helvetiker.<br>
    fontWeight: "bold", // regular, bold. defaults to regular.<br>
    align: "left", // left, center, right. defaults to left.<br>
    holes: true, // boolean. defaults to true.<br>
    cut: "solid", // solid, dashed. default to solid.<br>
    dashPercent: 20, // integer from 0 to 100. defaults to 20<br>
    mode: "laser", // laser, mill. defaults to laser.<br>
    laseron: "m3", // m3, m7. defaults to m3.<br>
    feedrate: 200, // integer. defaults to 200<br>
}
</td></tr>    
      </tbody>
  </table>

## Foreign Publish

This widget/element publishes to the following signals that are owned by other objects. 
To better understand how ChiliPeppr's subscribe() method works see amplify.js's documentation at http://amplifyjs.com/api/pubsub/

  <table id="com-chilipeppr-elem-pubsubviewer-foreignpub" class="table table-bordered table-striped">
      <thead>
          <tr>
              <th style="">Signal</th>
              <th style="">Description</th>
          </tr>
      </thead>
      <tbody>
      <tr valign="top"><td>/com-zipwhip-widget-font2gcode/com-chilipeppr-widget-3dviewer/request3dObject</td><td>This gives us back the 3d object from the 3d viewer so we can add Three.js objects to it.</td></tr>    
      </tbody>
  </table>

## Foreign Subscribe

This widget/element publishes to the following signals that are owned by other objects.
To better understand how ChiliPeppr's publish() method works see amplify.js's documentation at http://amplifyjs.com/api/pubsub/

  <table id="com-chilipeppr-elem-pubsubviewer-foreignsub" class="table table-bordered table-striped">
      <thead>
          <tr>
              <th style="">Signal</th>
              <th style="">Description</th>
          </tr>
      </thead>
      <tbody>
      <tr valign="top"><td>/com-zipwhip-widget-font2gcode/com-chilipeppr-widget-3dviewer/recv3dObject</td><td>By subscribing to this we get the callback when we /request3dObject and thus we can grab the reference to the 3d object from the 3d viewer and do things like addScene() to it with our Three.js objects.</td></tr>    
      </tbody>
  </table>

## Methods / Properties

The table below shows, in order, the methods and properties inside the widget/element.

  <table id="com-chilipeppr-elem-methodsprops" class="table table-bordered table-striped">
      <thead>
          <tr>
              <th style="">Method / Property</th>
              <th>Type</th>
              <th style="">Description</th>
          </tr>
      </thead>
      <tbody>
      <tr valign="top"><td>id</td><td>string</td><td>"com-zipwhip-widget-font2gcode"<br><br>The ID of the widget. You must define this and make it unique.</td></tr><tr valign="top"><td>name</td><td>string</td><td>"Widget / Font2Gcode"</td></tr><tr valign="top"><td>desc</td><td>string</td><td>"This widget lets you type text, render it into the 3D viewer, and then generate the gcode for the font. If you want to mill/laser/print text this is a great way to do it programmatically."</td></tr><tr valign="top"><td>url</td><td>string</td><td>"http://raw.githubusercontent.com/chilipeppr/widget-font2gcode/master/auto-generated-widget.html"</td></tr><tr valign="top"><td>fiddleurl</td><td>string</td><td>"http://ide.c9.io/chilipeppr/widget-font2gcode"</td></tr><tr valign="top"><td>githuburl</td><td>string</td><td>"http://github.com/chilipeppr/widget-font2gcode"</td></tr><tr valign="top"><td>testurl</td><td>string</td><td>"http://widget-font2gcode-chilipeppr.c9users.io/widget.html"</td></tr><tr valign="top"><td>publish</td><td>object</td><td>Please see docs above.<br><br>Define the publish signals that this widget/element owns or defines so that
other widgets know how to subscribe to them and what they do.</td></tr><tr valign="top"><td>subscribe</td><td>object</td><td>Please see docs above.<br><br>Define the subscribe signals that this widget/element owns or defines so that
other widgets know how to subscribe to them and what they do.</td></tr><tr valign="top"><td>foreignPublish</td><td>object</td><td>Please see docs above.<br><br>Document the foreign publish signals, i.e. signals owned by other widgets
or elements, that this widget/element publishes to.</td></tr><tr valign="top"><td>foreignSubscribe</td><td>object</td><td>Please see docs above.<br><br>Document the foreign subscribe signals, i.e. signals owned by other widgets
or elements, that this widget/element subscribes to.</td></tr><tr valign="top"><td>isSilent</td><td>boolean</td><td></td></tr><tr valign="top"><td>init</td><td>function</td><td>function (opts) <br><br>All widgets should have an init method. It should be run by the
instantiating code like a workspace or a different widget.
You can pass init options in.
If you set silent to true then the widget will not render any information
to the 3D viewer, rather you can make pubsub calls to the widget instead
to get info like Gcode for your text without having it render. That way you
can do whatever you want with the Gcode.
{
silent: true, // default to false  
}</td></tr><tr valign="top"><td>isActivated</td><td>boolean</td><td></td></tr><tr valign="top"><td>activate</td><td>function</td><td>function () <br><br>Called by the workspace to activate this widget.</td></tr><tr valign="top"><td>unactivate</td><td>function</td><td>function () <br><br>Called by the workspace to deactivate this widget.</td></tr><tr valign="top"><td>init3d</td><td>function</td><td>function (callback) <br><br>Try to get a reference to the 3D viewer.</td></tr><tr valign="top"><td>setupPubSub</td><td>function</td><td>function () <br><br>Setup the signals that can be published to this widget so other widgets/users
can interact with our functionality.</td></tr><tr valign="top"><td>getGcode</td><td>function</td><td>function (opts) <br><br>getGcode method attached the /getGcode pubsub method.
Pass in {
callback: yourmethod,
text: "my text",
size: 10, // mm. (float) Height of text.
fontName: "helvetiker", // helvetiker, optimer, gentilis, droid/droid_sans, droid/droid_serif. defaults to helvetiker.
fontWeight: "bold", // regular, bold. defaults to regular.
align: "left", // left, center, right. defaults to left.
holes: true, // boolean. defaults to true.
cut: "solid", // solid, dashed. default to solid.
dashPercent: 20, // integer from 0 to 100. defaults to 20
mode: "laser", // laser, mill. defaults to laser.
laseron: "m3", // m3, m7. defaults to m3.
feedrate: 200, // integer. defaults to 200
}</td></tr><tr valign="top"><td>btnSetup</td><td>function</td><td>function () <br><br>Call this method from init to setup all the buttons when this widget
is first loaded. This basically attaches click events to your 
buttons. It also turns on all the bootstrap popovers by scanning
the entire DOM of the widget.</td></tr><tr valign="top"><td>isChanging</td><td>boolean</td><td></td></tr><tr valign="top"><td>onChange</td><td>function</td><td>function () </td></tr><tr valign="top"><td>onRender</td><td>function</td><td>function (callback) </td></tr><tr valign="top"><td>getSettings</td><td>function</td><td>function () </td></tr><tr valign="top"><td>sendGcodeToWorkspace</td><td>function</td><td>function ()</td></tr><tr valign="top"><td>generatedGcodeForText</td><td>string</td><td></td></tr><tr valign="top"><td>generateGcode</td><td>function</td><td>function (altGrp, opts) <br><br>Iterate over the text3d that was generated and create
Gcode to mill/cut the three.js object.</td></tr><tr valign="top"><td>drawText</td><td>function</td><td>function (callback) <br><br>Draw the text to the 3D viewer based on the user settings
in the widget.</td></tr><tr valign="top"><td>createText</td><td>function</td><td>function (text, options, callback) <br><br>Create text in Three.js.<br>
Params: createText(text, options)<br>
text - The text you want to render<br>
options - a set of options to tweak the rendering<br><pre>
{
fontName : String. helvetiker, optimer, gentilis, droid sans, droid serif
fontWeight: String. regular, bold
size: Float. Size of the text as in the height.
align: String. "left", "center"
holes: Boolean. Whether to generate hole paths or not, like middle of a zero.
dashed: Boolean. If true then every other line is rendered in wireframe, rather than solid lines.
curveSegments: Integer. Number of points on the curves. Default is 12.
}</pre></td></tr><tr valign="top"><td>fontLoaded</td><td>object</td><td></td></tr><tr valign="top"><td>loadFont</td><td>function</td><td>function (fontOpts, callback) </td></tr><tr valign="top"><td>onInit3dSuccess</td><td>function</td><td>function () </td></tr><tr valign="top"><td>obj3d</td><td>object</td><td></td></tr><tr valign="top"><td>obj3dmeta</td><td>object</td><td></td></tr><tr valign="top"><td>userCallbackForGet3dObj</td><td>object</td><td></td></tr><tr valign="top"><td>get3dObj</td><td>function</td><td>function (callback) </td></tr><tr valign="top"><td>get3dObjCallback</td><td>function</td><td>function (data, meta) </td></tr><tr valign="top"><td>is3dViewerReady</td><td>boolean</td><td></td></tr><tr valign="top"><td>clear3dViewer</td><td>function</td><td>function () </td></tr><tr valign="top"><td>mySceneGroup</td><td>object</td><td></td></tr><tr valign="top"><td>sceneReAddMySceneGroup</td><td>function</td><td>function () </td></tr><tr valign="top"><td>sceneRemoveMySceneGroup</td><td>function</td><td>function () </td></tr><tr valign="top"><td>sceneDisposeMySceneGroup</td><td>function</td><td>function () </td></tr><tr valign="top"><td>onHelloBtnClick</td><td>function</td><td>function (evt) <br><br>onHelloBtnClick is an example of a button click event callback</td></tr><tr valign="top"><td>options</td><td>object</td><td>User options are available in this property for reference by your
methods. If any change is made on these options, please call
saveOptionsLocalStorage()</td></tr><tr valign="top"><td>setupUiFromLocalStorage</td><td>function</td><td>function () <br><br>Call this method on init to setup the UI by reading the user's
stored settings from localStorage and then adjust the UI to reflect
what the user wants.</td></tr><tr valign="top"><td>saveOptionsLocalStorage</td><td>function</td><td>function () <br><br>When a user changes a value that is stored as an option setting, you
should call this method immediately so that on next load the value
is correctly set.</td></tr><tr valign="top"><td>showBody</td><td>function</td><td>function (evt) <br><br>Show the body of the panel.
<br><br><b>evt</b> ({jquery_event})  - If you pass the event parameter in, we 
know it was clicked by the user and thus we store it for the next 
load so we can reset the user's preference. If you don't pass this 
value in we don't store the preference because it was likely code 
that sent in the param.</td></tr><tr valign="top"><td>hideBody</td><td>function</td><td>function (evt) <br><br>Hide the body of the panel.
<br><br><b>evt</b> ({jquery_event})  - If you pass the event parameter in, we 
know it was clicked by the user and thus we store it for the next 
load so we can reset the user's preference. If you don't pass this 
value in we don't store the preference because it was likely code 
that sent in the param.</td></tr><tr valign="top"><td>forkSetup</td><td>function</td><td>function () <br><br>This method loads the pubsubviewer widget which attaches to our 
upper right corner triangle menu and generates 3 menu items like
Pubsub Viewer, View Standalone, and Fork Widget. It also enables
the modal dialog that shows the documentation for this widget.<br><br>By using chilipeppr.load() we can ensure that the pubsubviewer widget
is only loaded and inlined once into the final ChiliPeppr workspace.
We are given back a reference to the instantiated singleton so its
not instantiated more than once. Then we call it's attachTo method
which creates the full pulldown menu for us and attaches the click
events.</td></tr>
      </tbody>
  </table>


## About ChiliPeppr

[ChiliPeppr](http://chilipeppr.com) is a hardware fiddle, meaning it is a 
website that lets you easily
create a workspace to fiddle with your hardware from software. ChiliPeppr provides
a [Serial Port JSON Server](https://github.com/johnlauer/serial-port-json-server) 
that you run locally on your computer, or remotely on another computer, to connect to 
the serial port of your hardware like an Arduino or other microcontroller.

You then create a workspace at ChiliPeppr.com that connects to your hardware 
by starting from scratch or forking somebody else's
workspace that is close to what you are after. Then you write widgets in
Javascript that interact with your hardware by forking the base template 
widget or forking another widget that
is similar to what you are trying to build.

ChiliPeppr is massively capable such that the workspaces for 
[TinyG](http://chilipeppr.com/tinyg) and [Grbl](http://chilipeppr.com/grbl) CNC 
controllers have become full-fledged CNC machine management software used by
tens of thousands.

ChiliPeppr has inspired many people in the hardware/software world to use the
browser and Javascript as the foundation for interacting with hardware. The
Arduino team in Italy caught wind of ChiliPeppr and now
ChiliPeppr's Serial Port JSON Server is the basis for the 
[Arduino's new web IDE](https://create.arduino.cc/). If the Arduino team is excited about building on top
of ChiliPeppr, what
will you build on top of it?

