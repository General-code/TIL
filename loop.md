### [BACK TO TIL](https://github.com/General-code/TIL/blob/main/README.md)

```javascript
let todos = [
  'clean room',
  'brush teeth',
  'exercise',
  'study javascript',
  'eat healthy!',
];

// Warning!!! Wrong code
// for(let i = 0; i < todos.length; i++){
//     todos.pop();
// }

// above code should be written in this way
// let todoLength = todos.length;
// for (let i = 0; i < todos.length; ++i) {
//   todos.pop();
// }
// Cause todos.length affected by the states of current todos.

// let counterOne = 0;

// while (counterOne < 10) {
//   console.log(counterOne);
//   counterOne++;
// }

// let coutnerTwo = 10;

// do {
//   console.log(coutnerTwo);
//   coutnerTwo++;
// } while (coutnerTwo < 10);
// Check a condition after an execution
```
