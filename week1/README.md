# Tuesday

1. Ensure Question

Given a string, write a function that returns the string with a question mark ("?") appends to the end, unless the original string ends with a question mark, in which case, returns the original string.

- Solution

```js
function ensureQuestion(s) {
  size = s.length
  
  if (s[size-1]=='?') {
    return s
  } else {
    return s+'?'
  }
}
```

2. Reversed Words
Complete the solution so that it reverses all of the words within the string passed in.
Complete the solution so that it reverses all of the words within the string passed in.

- solution

```js
function reverseWords(str){
  array = str.split(' ')
  var newStr = ''
  for (let i=array.length-1; i>=0; i--){
    if (i===0) {
      newStr += array[i]
    } else {
      newStr += array[i] + ' '
    }    
  }
  
  return newStr;
}
```

# Wednesday

1. Smallest Integer In Array

Given an array of integers your solution should find the smallest integer.

- solution

```js
class SmallestIntegerFinder {
  findSmallestInt(args) {
    args.sort((a,b)=>a-b);
    return args[0]
  }
}
```

# Thursday

1. Odd Or Even 

Given a list of integers, determine whether the sum of its elements is odd or even.

Give your answer as a string matching "odd" or "even".

If the input array is empty consider it as: [0] (array with a zero).

- solution

```js
function oddOrEven(array) {   
  if (array.length ===0){
    return 'even'
  }
  const sum = array.reduce((a, b) => a+b)
  if (sum % 2 === 0 ) {
    return 'even'
  } else {
    return 'odd'
  }
}

```
