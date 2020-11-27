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

### Javascript DOM Manipulation
- When manipulating DOM Elements you can use querySelector("") and add class to the selected element writing code like this querySelector(".class").classList.add("invisible");
  - classList returns class list of an selected Element and there are it's methods such as **toggle, add, remove** 
  - You can gather all same elements using querySelectorAll then it will returns lists of the same elements. 
- **Every CSS property are camel case in javascript**, So you should remove hyphen and change that property into the camel case.
- when you **change CSS sytle uisng (some element Selected by selector).style.color = "value";** all the property value in javascript should be wrapped with "" so it would be the string

- innerHTML vs textContent 
  - innerHTML returns the literally all the written things inside an selected element 
  - textContent returns only text of an selected element
  
- Manipulating attribute of an HTML element
  - you can get array of attributes of an element using .attributes;
  - you can see specific attribute using .getAttribute('attribute name');
  - change attribute .setAttribute('Attribute you are going to change', 'what you are going to change it to');
  
  
- addEventListener(type, function) throught this code you can add function to be called when listeners listen to the specific type behavior
- you can use debugger; in chrome developer tool
- We can **pass the event that trigers eventListener as a parameter to the function associated with the event listener**
- it's also possible for the entire web page to listen(wait for) to the event.(use document)
```javascript
      document.addEventListener('keydown',function(event){
        console.log(event);
      });
```

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
        eventType: "Keypress",
        key: "p",
        durationOfKeyPress: 2
    }

    if (eventThatHappened.eventType === typeOfEvent) {
      callback(EventThatHappened);
      }
    }
```




