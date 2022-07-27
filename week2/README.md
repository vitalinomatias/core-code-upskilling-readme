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

# Wednesday

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

