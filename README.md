# TIL
Today I learned


## About Front-end Programming Design
2020.11.18
[Manage ATTENTION with effective User Interface](https://github.com/General-code/TIL/blob/main/Front-end%20Design%20Princple.md)


## ISSUES
🤷‍♂️🤷‍♀️ Wihle I am coding at sparta I suddenly encountered some bootstrap related erros
  - [x] I used combination of grid and card but some errors occured. there should be 4 cards in a line when the view-port is desktop-size and should 2 cards with the same size in the small size. but the size of first card was different!!!😱😱 
    - use meta tag viewport
  - [x] Bootstrap, CSS, and other media sources didn't exist on the webpage from my localhost flask server. And Tutor Chan Ho Lee helped me to find out the cause of that error. It was casued from the flask's folder structure. I didn't placed css code and media files in the static folder. And After I **moved them from template directory to the static file directory. Everything was clear** 

- I suffered from some issues with forwarding a little information when I request for some informations rendering other HTMLfile. But It was resolved by using request's library. 
  > ex 
  
  ```python
    title = request.args.get('title')
    return render_template('show.html',title=title)
  ```

## Javascript

### [Javascript DOM Manipulation](https://github.com/General-code/TIL/blob/main/Javascript%20DOM%20manipulation.md)


### Javascript Object and Functions
- You have to make many of same type object? You want to pump them out like a factory?
  - use Constructor Function 
> like this use UpeerCase at each first word not camel casing and you must use new to give it a memory space 
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

- **After the Event has happened, the event Object is constructed based on that event and then the call back function gets it as an argument.
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


### Javascript Variables Delcaration
- **let** has block level scope
- **var** has function level scope and can be redeclared. This should be completely avoided. It's scope level is so weird.
- **const** used for constant variable yes It is used for immutable variable. Feature ** should be initiallized with an declaration.

```javascript
  lastName = 'Programmer'
  //this kind of code makes globlal variable.

```


- **Template Literals** can assemble mulitiple piece of code in one string.
```javascript
  let nation = 'korea'
  let temp = `My country is ${nation}
  and this is multiple
  line`;
```

- **Type conversion**
  - Use Number() to make a string number a computable number. If the string is made of non-numeric letter then the result is going to be NaN
  - String() all the type conversion start off with a uppercase letter.
- **Automatic Type coercion**
  - Basically happens when there is a operation between diffrent data types.
  - like number + string => string


#### Javascript Array
- Array declaration
```javascript
const friends = ['kim', 'ho', 'pu']
const years = new Array(1991, 1984, 2008, 2020);
const jonas = ['jonas', 10];
```
- the rest of this is same with the other programming langues it
- yet this has length property and cna have any type of data
