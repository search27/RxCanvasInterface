# RxCanvasInterface
RxCanvasInterface

* Create UI/UX Element Into Canvas
* Support By [ Cloud Rx (<a href='https://rxapis.com'>https://rxapis.com</a>) ].
* Testing is available until the end of the year.

## Version
* Test Version - UnStable

## Step Folder
* Step1.html - Create Button
* Step2.html - Create SelectBox
* Step3.html - Create Slider
* Step4.html - Zoom And Move Sample

## Sample Code

```javascript
// target, Create Canvas Count : default 1
const interface = new RxCanvasInterface.Interface(document.body, 2);
const canvas = interface.GetCanvas();

// Mouse Events
const mouseEvt = new RxCanvasInterface.MouseEvents();

// Setting Mouse Events
interface.SetMouseEvents(mouseEvt);


interface.SetGrid([10, 10]);
interface.SetGridVisualize(true);
interface.SetCollisionVisualize(true);           // default : false


const center = [ window.innerWidth / 2, window.innerHeight / 2];
const size = 100;   // width, height
const button = new RxCanvasInterface.Button(center[0], center[1], size, size);
button.SetClickCallback((self) => {
    console.log('clicked');
    console.log(self);
})

const buttonSelf = button.GetSelf();
interface.AddComponent(buttonSelf);
interface.AddCollision(buttonSelf);

```

## Interface
* This is Controller For Each Elements




## Common

## Properties
### DefaultProperties

```javascript
console.log(RxCanvasInterface.DefaultProperties);
console.log(RxCanvasInterface);             // Check Functions
```
### Common Elements Functions
```javascript
function GetSelf(){}                    // Get Self
function SetProperties(){}              // Set Properties Base on Default Properties
function IsCollision(){}                // Check Collision
function SetClickAction(){}
function SetClickCallback(){}
function SetPivot(){}                   // Not Support Yet
function CreatePivots(){}
function CreateEdge(){}
function DrawPolygon(){}
function DrawStroke(){}
function DrawText(){}
function BaseUpdate(){}
function BaseDraw(){}
```

## Grid
* Not Support Yet

## Function And Constructor
* CreateCanvas - Function( _target, _count, _isResize, interface )
* Interface - Constructor( wrapper, _count, isRenderSelf )
* CanvasMover - Constructor()
* MouseEvents - Constructor()

## Elements
* Grid - Not Support Yet
* Pivot - Not Support Yet
* 
### Button

```javascript

const center = [ window.innerWidth / 2 - (size / 2), window.innerHeight / 2 - (size / 2)];
const size = 100;   // width, height
const button = new RxCanvasInterface.Button(center[0], center[1], size, size);
button.SetClickCallback((self) => {
    console.log('clicked');
    console.log(self);
})
const buttonSelf = button.GetSelf();
interface.AddComponent(buttonSelf);
interface.AddCollision(buttonSelf);

```

### TextBox

```javascript

const center = [ window.innerWidth / 2 - (size / 2), window.innerHeight / 2 - (size / 2)];
const size = 100;   // width, height
const textbox = new RxCanvasInterface.TextBox(center[0], center[1], size, size);
const textboxSelf = textbox.GetSelf();
interface.AddComponent(textboxSelf);
interface.AddCollision(textboxSelf);

```


### SelectBox

```javascript

const selectBoxStyle = {
    text : 'Button Sample',
    lineWidth : 2,
    textAlign : 'center',
    textBaseline : 'middle',
    fontSize : 33,
    borderRadius : 10
};

const selectOptions = [
    { name : 'High', value : 2 },
    { name : 'Medium', value : 3 },
    { name : 'Low', value : 4 },
];
const optionsStyle = {
    textAlign : 'center',
    textBaseline : 'middle',
    fontSize : 30,
    color : 'red',
};

const width = 500;
const height = 100;
const center = [ window.innerWidth / 2 - (width / 2), window.innerHeight / 2 - (height / 2)];
const selectBox = new RxCanvasInterface.SelectBox(center[0], center[1], width, height);
selectBox.SetProperties(selectBoxStyle);
selectBox.SetOptions(selectOptions, optionsStyle);
selectBox.SetChangeCallback((option) => {
    console.log(option);
})
const selectSelf = selectBox.GetSelf();
interface.AddComponent(selectSelf);
interface.AddCollision(selectSelf);

```

### Slider

```javascript
const width = 500;
const height = 100;
const selectBoxStyle = {
    text : 'Button Sample',
    lineWidth : 2,
    textAlign : 'center',
    textBaseline : 'middle',
    fontSize : 33,
    borderRadius : 10
};

const sliderPropertiesWrapper = {
    width : width,
    height : height / 2,
    fontSize : 33,
    color : 'black',
    lineWidth : .5,
    strokeStyle : '#333',
    textAlign : 'center',
    textBaseline : 'middle',
    padding : 20,
};
const sliderProperties = {
    emptyColor : '#ccc',
    fillColor : '#00afd7',
    pointColor : '#b93640',
    pointRadius : 10,                       // Min Radius : this.Properties.height / 2
    min : 0,
    max : 100,
    value : 50,
};

const center = [ window.innerWidth / 2 - (width / 2), window.innerHeight / 2 - (height / 2)];
const slider = new RxCanvasInterface.Slider(center[0], center[1], width, height / 2);

slider.SetProperties(sliderPropertiesWrapper);
slider.SetSliderOption(sliderProperties);
slider.SetChangeCallback(function(value, self){
    console.log(value);
    console.log(self);
});
slider.update();

const sliderSelf = slider.GetSelf();
interface.AddComponent(sliderSelf);
interface.AddCollision(sliderSelf);

```



## Customize
## Overwrite Component

