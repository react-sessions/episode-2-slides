
## STATE

---

### State

- An object internal to a Component describing its... state
- Only available in class-based Components
- Initialized in the constructor
- [Change state](https://codepen.io/berkmolla/pen/rzGBKP) by calling `this.setState(...)`
- State changes trigger component updates
- State changes are [asynchronous](https://codepen.io/berkmolla/pen/mMBjGX?editors=1111)
- A component can't modify the state of other components
- Updating one part of the state results in a shallow merge into the main state object.

---

### But how is state different to props?

---

#### State vs. Props

| _props_ | _state_ |
--- | --- | ---
Can get initial value from parent Component? | Yes | Yes
Can be changed by parent Component? | Yes | No
Can set default values inside Component? | Yes | Yes
Can change inside Component? | No | Yes
Can set initial value for child Components? | Yes | Yes
Can change in child Components? | Yes | No

Taken from [this guide](https://github.com/uberVU/react-guide/blob/master/props-vs-state.md#changing-props-and-state)

---

<img src="img/statetweet.jpeg" width="550"></img>


---

### [Exercise](https://codepen.io/berkmolla/pen/YxvGWz)


---

[Solution](https://codepen.io/berkmolla/pen/mMBGGg)
