# RxCanvasInterface
RxCanvasInterface

* Create UI/UX Element Into Canvas

* Support By [ Cloud Rx (<a href='https://rxapis.com'>https://rxapis.com</a>) ].
* Testing is available until the end of the year.

## Version
* Test Version - UnStable


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
button.SetPivot(4);

const buttonSelf = button.GetSelf();
interface.AddComponent(buttonSelf);
interface.AddCollision(buttonSelf);

```

## Interface
* This is Controller For Each Elements




## Common

## Properties
## Grid

## Elements
* Grid
* Pivot
*
### Button

```javascript

const center = [ window.innerWidth / 2, window.innerHeight / 2];
const size = 100;   // width, height
const button = new RxCanvasInterface.Button(center[0], center[1], size, size);
button.SetClickCallback((self) => {
    console.log('clicked');
    console.log(self);
})
button.SetPivot(4);

const buttonSelf = button.GetSelf();
interface.AddComponent(buttonSelf);
interface.AddCollision(buttonSelf);

```




## Customize
## Overwrite Component

