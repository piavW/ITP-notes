<h1> My notes about the The Document Object Model (DOM)</h1>
<i> A lot of info can be found https://developer.mozilla.org/en-US/</i>

As long as there is a <div> we can access and queary it's contents. 

.querySelectorAll() is slower than .getElementsByTagName() the former takes a snapshot of what is in the document and created a NodeList not an array. The .getElementsByTagName() is faster in all browsers and is live i.e. it updates according to how the document it manipulated. 

<h2> To create an array from a created NodeList </h2>
```js
 Array.from(myElements).forEach(doSomethingWithEachElement)
// Or prior to ES6
Array.prototype.forEach.call(myElements, doSomethingWithEachElement)
// Shorthand:
[].forEach.call(myElements, doSomethingWithEachElement)
```

Read-only properties referencing the family - all are live.

```js
myElement.children
myElement.firstElementChild
myElement.lastElementChild
myElement.previousElementSibling
myElement.nextElementSibling
```
As the Element interface inherits from the Node interface, the following properties are also available:

```js
myElement.childNodes
myElement.firstChild
myElement.lastChild
myElement.previousSibling
myElement.nextSibling
myElement.parentNode
myElement.parentElement
``` 

We can then check the type of a given node like e.g.

```js
const myElement = document.querySelector('#foo div.bar')
myElement.firstChild.nodeType === 3
// this would be a text node
//As with any object, we can check a node’s prototype chain using the instanceof operator:
myElement.firstChild instanceof Text
```

To modify classes of elements:
```js
myElement.classList.add('foo')
myElement.classList.remove('bar')
myElement.classList.toggle('baz')
``` 

To access and modofy element properties: 
```js
// Get an attribute value
const value = myElement.value
// Set an attribute as an element property
myElement.value = 'foo'
// Set multiple properties using Object.assign()
Object.assign(myElement, {
  value:'foo',
  id:'bar'})
// Remove an attribute
myElement.value = null
// the following method modify the HTML attricbutes directly which causes a browser redraw... be cautious 
.getAttribute()
.setAttribute()
.removeAttribute()
```

<b> CSS styles</b>
<i>All properties are camelCased in JavaScript!</i>
If we want certain values, we can obtain these via the .style property. However, this will only give us styles that have been explicitly applied. To get the computed values, we can use, .window.getComputedStyle() which returns a CSS Style Delaraction. 

<h2> Modifying the DOM </h2>
We can move elements:
// Append element1 as the last child of element2
element1.appendChild(element2)// Insert element2 as child of element 1, right before element3
element1.insertBefore(element2, element3)
If we don’t want to move the element, but insert a copy, we can clone it like this:

// Create a cloneconst myElementClone = myElement.cloneNode()
myParentElement.appendChild(myElementClone)
The .cloneNode() method optionally takes a boolean as an argument if set to true, a deep_copy will be created, meaning its children are also cloned.

Changing the inner HTML isn't very advised, also if you use the .onclick for eventlistener you can't add additional listeners. 
```js
myElement.onclick =function onclick (event){
  console.log(event.type +' got fired')
  }
```
Use .addEventListener() instead. It takes three arguments: the event type (such as click), a function that gets called whenever the event occurs on the element (this function gets passed an event object), and an optional config object which can have boolean properties: .capture (triggered before any other element beneath it in DOM), .once (happens once), .passive(it will be ignored) (all of which default to false). Because .capture is so common there is a shorthand: myElement.addEventListener(type, listener,true);
```js
myElement.addEventListener('click',function(event){
  console.log(event.type +' got fired')})

myElement.addEventListener('click',function(event){
  console.log(event.type +' got fired again')})
```
Commong evenlistener is the DOMContentLoaded triggered when window or document object is fully loaded. 
```js
window.addEventListener('DOMContentLoaded', function () {
    // Window has loaded!
    console.log('Window has loaded! Event type: ' + event.type);
});

document.addEventListener('DOMContentLoaded', function () {
    // Document has loaded!
    console.log('Document has loaded! Event type: ' + event.type)
});
// There is also the "load" triggered when the entire thing html, images etc is loaded. the Load event isn't triggered on 'document'
window.addEventListener('load', function(){
  // Everything has loaded!
  console.log('Everything has loaded!);
});
```
.removeEventListener() removes the eventlistener. 

.preventDefault() prevents the browser's default behaviour, like following a link. 

Another common use-case would be to conditionally prevent the submission of a form if the client-side form-validation fails. Something like this:
```js
myForm.addEventListener('submit', function (event) {
    const name = this.querySelector('#name')
    if (name.value === 'Thomas') {
        alert('Hi Coach! Why are you submitting this?');
        event.preventDefault();
    }
});
```
Another important event method is .stopPropagation(), which will prevent the event from bubbling up the DOM. This means that if we have a propagation-stopping click listener on an element, and another click listener on one of its parents, a click event that gets triggered on the child element won’t get triggered on the parent — otherwise, it would get triggered on both.

<h2> Animations </h2>
Use the function window.requestAnimationFrame() instead of the function window.setTimeout()
```js
// fade out
function fadeOut(el) {
    el.style.opacity = 1;

    (function fade() {
        if ((el.style.opacity -= .1) < 0) {
            el.style.display = "none";
        } else {
            requestAnimationFrame(fade);
        }
    })();
}

// fade in
function fadeIn(el) {
    el.style.opacity = 0;
    el.style.display = "block";

    (function fade() {
        var val = parseFloat(el.style.opacity);
        if (!((val += .1) > 1)) {
            el.style.opacity = val;
            requestAnimationFrame(fade);
        }
    })();
}
```

