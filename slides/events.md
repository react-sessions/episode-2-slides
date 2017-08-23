<img src="img/react.svg" class="spin logo logo--small" />

## Events

------

Events are handled in a similar way to handling events on DOM elements with a few differences.

---

React events are named using camelCase rather than lowercase, and a function is passed as the event handler, rather than a string.

---

HTML click event:

```html
<button onclick="activateLasers()">
  Activate Lasers
</button>
```

React click event:

```html
<button onClick={activateLasers}>
  Activate Lasers
</button>
```

---

You can't return false to prevent default behaviour in React, instead you have to call preventDefault explicitly.

---

HTML:

```js
document.querySelector('.click').addEventListener('click', () => {
    return false;
});
```

React:

```js
const ActionLink = () => {
    const handleClick = event => {
        event.preventDefault();
    }

    return (
        <a href="#" onClick={handleClick}>Click me</a>
    )
}
```

---

### A Basic Event

```js
const activateLasers = () => console.log('Lasers activated!');

const App = () =>
    <button onClick={activateLasers}>Activate lasers</button>;
```

[<small>CodePen</small>](https://goo.gl/vcYZ8v)

---

### passing events via props

Events can be passed via props

```js
const activateLasers = () => console.log('Lasers activated!');

const App = props =>
    <button onClick={props.onActivateLasers}>
        Activate lasers
    </button>;

ReactDOM.render(
    <App onActivateLasers={activateLasers} />,
    document.getElementById('app')
);
```

[<small>CodePen</small>](http://goo.gl/k9TEG8)

---

Event handlers are triggered by an event in the bubbling phase. To register an event handler for the capture phase, append Capture to the event name; for example, instead of using onClick, you would use onClickCapture to handle the click event in the capture phase.

[Bubbling phase](http://goo.gl/iKax8R) — [Capture phase](http://goo.gl/Bw5fJw)

------

## Synthetic Events

![Spineshank Synthetic music video screenshot](img/spineshank-synthetic.jpg)

---

When you specify an event in React you are not dealing directly with DOM events. Instead, you are dealing with a React-specific event type known as a `SyntheticEvent`; a cross-browser wrapper around the browser's native event.

---

### Supported Events

```
Clipboard Events
Composition Events
Keyboard Events
Focus Events
Form Events
Mouse Events
Selection Events
Touch Events
UI Events
Wheel Events
Media Events
Image Events
Animation Events
Transition Events
```

---

React defines these synthetic events according to the [W3C spec](https://www.w3.org/TR/DOM-Level-3-Events/).

---

React normalizes events so that they have consistent properties across different browsers.


---

### `SyntheticEvent` properties

`SyntheticEvent` objects have the following properties:

```
boolean bubbles
boolean cancelable
DOMEventTarget currentTarget
boolean defaultPrevented
number eventPhase
boolean isTrusted
DOMEvent nativeEvent
void preventDefault()
boolean isDefaultPrevented()
void stopPropagation()
boolean isPropagationStopped()
DOMEventTarget target
number timeStamp
string type
```

---

If you need the underlying browser event you can access it via `event.nativeEvent`.

---

When using different types of events, more properties are sometimes available e.g. for keyboard events the following additional properties are available:

```js
boolean altKey
number charCode
boolean ctrlKey
boolean getModifierState(key)
string key
number keyCode
string locale
number location
boolean metaKey
boolean repeat
boolean shiftKey
number which
```

---

You access these properties like so:

```js
const activateLasers = e => console.log(e.shiftKey);
```

[<small>CodePen</small>](https://goo.gl/3k5jji)

------

## Event Pooling

---

The `SyntheticEvent` is pooled. This means that the `SyntheticEvent` object will be reused and all properties will be nullified after the event callback has been invoked.

This is for performance reasons. As such, you cannot access the event in an asynchronous way.

[<small>CodePen</small>](https://goo.gl/UzoHYs)

---

If you want to access the event properties in an asynchronous way, you should call `event.persist()` on the event, which will remove the synthetic event from the pool and allow references to the event to be retained by user code.

------

## Exercise

Create an component which writes a message to the console when the mouse is hovered over an element, and when the mouse is moved away from the element.

[CodePen](https://goo.gl/xLZZTt)

---

A solution

[CodePen](https://goo.gl/HP77kSt)

