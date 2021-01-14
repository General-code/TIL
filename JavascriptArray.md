## [Return to the TIL](https://github.com/General-code/TIL)
#### Javascript Array
- Array declaration
```javascript
const friends = ['kim', 'ho', 'pu']
const years = new Array(1991, 1984, 2008, 2020);
const jonas = ['jonas', 10];
```
- the rest of this is same with the other programming langues it
- yet this has length property and can have any type of data

- **push** method
  ```javascript
  frineds.push('korea') // (4)['kim', 'ho', 'pu', 'korea']\
  ```
  - Add element to the end of the array and returns the length of the array
- **unshift** method
  - Add element to the beginning of the array by passing argument in it.
- **pop** method
  - remove a last element so we don't need to pass any argument.
  - returns the removed data
- **shift** method
  - remove a value from the beginning of the array and return removed data.

  

- **indexOf** method
  - return the index of an value. if it doesn't exit return -1

- **includes** method
  - reutun true or false
  - strict to checking the equality.
  - useful to conditional statement.

- **concat** method
  - get list as a parameter
  - return merged list but don't change the state of object which use this method.
  
- **splice** method
  - remove data including start position and excluding end position.
```javascript
   array.splice(0,1) // same with array.shift()
```

- **sort** method
  - make array sorted.
  - don't have to assign code itself. 
  
  
- **reverse** moethod
  - reverse array order. 
  - don't have to assign code itself.


- **forEach** method 
  - make code more succint and unifed
```javascript
function logTodos(todo, i) {
  console.log(todo, i);
}
todos.forEach(logTodos);
clean room 0
brush teeth 1
exercise 2
study javascript 3
eat healthy! 4
```
> !When you pass just one argument to a function. It will pass the value in the object.
