# Monday

1. Monday

A palindrome is a word, phrase, number, or other sequence of characters which reads the same backward or forward. This includes capital letters, punctuation, and word dividers.

Implement a function that checks if something is a palindrome. If the input is a number, convert it to string first.

Examples(Input ==> Output)

- Solution

```js
function isPalindrome(line) {

  let palindromo = line.toString()
  palindromo = palindromo.split('').reverse()
  palindromo = palindromo.join('')

  if (line.toString() === palindromo){
    return true
  } else {
    return false
  }
  
}
```

# Tuesday

1. Well Of Ideas

For every good kata idea there seem to be quite a few bad ones!

In this kata you need to check the provided array (x) for good ideas 'good' and bad ideas 'bad'. If there are one or two good ideas, return 'Publish!', if there are more than 2 return 'I smell a series!'. If there are no good ideas, as is often the case, return 'Fail!'.

Solution

```js
function well(x){
  busqueda = x.filter(elemento => elemento == 'good').length
  if (busqueda === 1 || busqueda ===2) {
    return 'Publish!'
  } else if (busqueda > 2) {
    return 'I smell a series!'
  } else {
    return 'Fail!'
  }
}
```

# Wednesday

1. React Manage Events

Write a react component that will display the current value of our counter.

The counter should start at 0.
There should be a button to add 1.
There should also be a button to subtract 1.
We want to be able to see the value of the counter - so it should be rendered! And for your buttons to work they will need an onClick prop.

In your render you should return:

The counter display element with an id of 'counter', containing the counter value.
An increment button with an id of 'increment'
A decrement button with an id of 'decrement'

```js
import React from 'react';

export class Counter extends React.Component {
  constructor(props) {
    // Your state
    super(props);
    this.state = {
      counter:0
    }
    this.decrement = this.decrement.bind(this)
    this.increment = this.increment.bind(this)
  }
  
  // Your event handlers 
  
  decrement() {
    this.setState({
      counter: this.state.counter -1
    })
  }
  
  increment() {
    this.setState({
      counter: this.state.counter +1
    })
  }
  
  render() {
    return (
      <div>
        <h1 id="counter">{this.state.counter}</h1>
          <button type="button" id="decrement" onClick={this.decrement}>
            Decrement
          </button>
          <button type="button" id="increment" onClick={this.increment}>
            Increment
          </button>
      </div>
    )
  }
}
```

# Thursday

1. React Santa Wish List

Santa wants to simplify his life and offer children the possiblity to enter their wishlist via an online form.

The form should be a React component and should contain:

an input field for the child's name (with id 'name')
a text area to describe the wish (id: 'wish')
a drop-down indicating the priority of the wish, from 1 to 5 - default is 1 (id: 'priority')
the keys in the state to store the corresponding values should be named the same as the element's id
an onSubmit action calling the function handleSubmit
a function called handleSubmit, which
calls send (a function that is already provided as part of the injected properties props)
passes the current state as a parameter to send
calls event.preventDefault
it should be a controlled component (i.e. using onChange to bind input to the component's state)

```js
const React = require("react");

class WishlistForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = { name: '', wish: '', priority: 1 };
    this.name = this.name.bind(this);
    this.wish = this.wish.bind(this);
    this.priority = this.priority.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }
  
  name(event) {
    this.setState({name: event.target.value});
  }
  
  wish(event) {
    this.setState({wish: event.target.value});
  }
  
  
  priority(event) {
    this.setState({priority: event.target.value});
  }
  
  handleSubmit(event){
    event.preventDefault();
    this.props.send(this.state);
  }
  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <label>
            Name
            <input type="text" id="name" value={this.state.name} onChange={this.name}/>
        </label>

        <label>
            wish
            <textarea  id="wish" value={this.state.wish} onChange={this.wish} />
        </label>

        <label>
            Wish Priority:
            <select value={this.state.priority} id="priority" onChange={this.priority}>
                <option value='1'>1</option>
                <option value='2'>2</option>
                <option value='3'>3</option>
                <option value='4'>4</option>
                <option value='5'>5</option>
            </select>
        </label>
       
      <input type="submit" value="Submit" />
      </form>
    );
  }
};
```