## TIL[https://github.com/General-code/TIL]
### Javascript Object and Functions

### Function delcaration
- **Function declaration** allows to use the function before the declaration because of hoisting
```javascript
   cal(3,5);
   function cal(a, b) {
    return a - b;
    }
```
- **Function expression** doesn't allow to use the function before the initialization. (This is also hoisted but I will talke the principle of hoisting and TDM later)
  - **In javascript function is actually just a value** so it's possible to assign it into a variable.
```javascript
   const cal2 = function (a,b){
    return a - b;
   }
```
- **Arrow function** is a short and special form of a function expression
  - added from the ES6
  - don't need curly braces so simple
  - implicit return statement
  - if you write multiple-line function and needs more than one parameter it would be super complex
  - and this is different from the normal function. 
  
```javascript
   const calcAge3 = birthYear => 2037 - birthYear;
   console.log(birthYear);
   
   // when to write down multi-line we need curly brace again
   // we should express return statement.
   
   const yearsUntilRetirement = (currentYear ,birthYear) => {
    const age = currentYear - birthYear;
    const retirement = 65 - age;
    if (retirement > 0)
      return retirement;
    else return -1;
    }
```



#### Javascript Object
- we can gather the related vairables giving them names.
```javascript
const obj = {
name : "kre",
birth : 2020,
skills : ['programming' , 'bungee jumping']
}
```
- ways to access the object's values
  - dot operation (simple, don't allow string operation)
    - member access
  - bracket operation (you can do many things such as string operation and using calling with the variable)
    - useful to computed Member Access
```javascript
   obj.name;
   obj.n + 'ame' // undefined
   obj['n' + 'ame'] // 'kre'
   let use = 'birth'
   obj[use]
```
  
- You have to make many of same type object? You want to pump them out like a factory?
  - use Constructor Function 
> like this use UpperCase at each first word not camel casing and you must use new keyword to give it a memory space 
```javascript
          function BellBoy(age, name, skills) {
            this.age = age;
            this.name = name;
            this.skills = skills;
          }
          
          let bellyBoy1 = new BellBoy(20, 'Pssion', ['limitless passion','speedy feet']);
 ```
 
- **Higher order function** is a function that gets a function as an input.
- **Callback function** is a function finishes the entire process of a higher order function. This is got passed into the higher order function as an input function.
- event that triggered this callback function  pass back through the call back function
- call back function is not triggered by us but an object experienced specific event

- **After the Event has happened, the event Object is constructed based on that event and then the call back function gets it as an argument.**
- and the event listener check if the type of event is same with the event listener is wating for. 

```javascript
    function anotherAddEventListener(typeOfEvent, callback) {

      //Dtect Event Code.. 

    let eventThatHappened = {
        eventType: "keydown",
        key: "p",
        durationOfKeyPress: 2
    }

    if (eventThatHappened.eventType === typeOfEvent) {
      callback(EventThatHappened);
      }
    }
```
