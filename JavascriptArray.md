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
