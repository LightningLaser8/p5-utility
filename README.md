# p5-utility
Helpful stuff for working with p5.js
## UIComponents: `UI`
Creates a user interface with buttons, sliders and selectors, without DOM manipulation (outside of p5's default stuff)  
Has the following properties: `createPropertySelector()`, `createUIImageComponent()`,  `createSliderComponent()`, `createUIComponent()`, `evaluateCondition()`, `setCondition()`, `setState()`, `font`, `bg`, `tick`, `uiFrame()`, `transform`
### createUIComponent
Creates a new UI component.  
The background will either be an image (set by `bg`) or a colour, if `setBackgroundColour` is used.
```js
function createUIComponent(
  screens = [], //UI states, or 'screens' to show on.
  conditions = [], //UI conditions that must all be true, unless the first one is the string "any", in which case any one can be true.
  x = 0, //X position.
  y = 0, //Y position.
  width = 1, //Width in pixels.
  height = 1, //Height in pixels.
  bevel = "none", //Chops off corners. "right" removes the bottom-right corner, "left" removes the top-left, "both" does both.
  onpress = null, //Function to execute on click of the component. Makes it a button.
  shownText = "", //Text to show on the button.
  shownTextSize = 20 //Size of the button's text.
)
```
### createUIImageComponent
```js
function createUIImageComponent(
  screens = [], //UI states, or 'screens' to show on.
  conditions = [], //UI conditions that must all be true, unless the first one is the string "any", in which case any one can be true.
  x = 0, //X position.
  y = 0, //Y position.
  width = 1, //Width in pixels.
  height = 1, //Height in pixels.
  onpress = null, //Function to execute on click of the component. Makes it a button.
  shownImage = null, //Image to draw.
  outline = true //If true, draws an outline around the image.
)
```
### createSliderComponent
Creates a slider.
```js
function createSliderComponent(
  screens = [], //UI states, or 'screens' to show on.
  conditions = [], //UI conditions that must all be true, unless the first one is the string "any", in which case any one can be true.
  x = 0, //X position.
  y = 0, //Y position.
  width = 1, //Width of the start block in pixels.
  sliderLength = 100, //Width of the slider part in pixels.
  height = 1, //Height of the start block  in pixels.
  bevel = "none", //Chops off corners. "right" removes the bottom-right corner, "left" removes the top-left, "both" does both.
  shownText = "", //Text to show on the button.
  shownTextSize = 20 //Size of the button's text.
  onchange = null, //Function to execute on slider value change.
  min = 0, //Minimum value (i.e. all the way to the left)
  max = 100  //Maximum value (i.e. all the way to the right)
)
```
### createPropertySelector
Creates a set of buttons to set a property of an object.
```js
function createPropertySelector(
  screens = [], //UI states, or 'screens' to show on.
  conditions = [], //UI conditions that must all be true, unless the first one is the string "any", in which case any one can be true.
  x = 0, //X position.
  y = 0, //Y position.
  bufferWidth = 1, //Width of starting block.
  optionWidth = 1, //Width of each option.
  height = 1, //Height of the selector.
  object = {}, //Object whose property to change.
  property = "", //Property name of that object to change.
  options = [""], //Array of values for options.
  defaultOption = null, //Option index to select at start.
  shownTexts = [""], //Array of texts for options.
  shownTextSize = 50, //Size of option text.
  onchange = (value) => { }
)
```
### setCondition
Sets property:value on game ui conditions: input "slot:1" sets "slot" to "1".  
This is used for conditional components.
### evaluateCondition
Evaluates property:value on game ui conditions: input "slot:1" returns true if "slot" is "1".  
This is used for conditional components.
### setState
Sets the ui's 'state', which is checked in all components for visibility.#
### uiFrame
Ticks and draws the ui. Will not tick if `tick` is set to false.
### transform
Holds options to change UI components:
```js
invert(uicomponent) //Turns a component's background upside-down.
setBackgroundOf(uicomponent, colour = null) //Makes a component use colour instead of an image.
removeOutline(uicomponent) //Removes that annoying outline.
setOutlineColour(uicomponent, colour = null) //Changes the colour of that annoying outline.
alignLeft(uicomponent) //Aligns a component to the left, instead of right.
```
### font
Text font to use.