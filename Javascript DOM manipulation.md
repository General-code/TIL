# DOM
- **Document Object Model** which is rendered when the loading of html file is finished.
- ✔**DOM and DOM methods are** not the part of the javascript(ecmascript). They are **just web API provided by web browser and can interact with javascript**
## Selecting Element
- getElementByTagName method returns the array of the specified type of tag.
### Working with Classes
- When manipulating DOM Elements you can use querySelector("") and add class to the selected element writing code like this **querySelector(".class").classList.add("invisible");**
  - **classList** returns class list of an selected Element and there are it's methods such as **toggle, add, remove** 
  - You can gather all same elements using querySelectorAll then it will returns lists of the elements have a selector in common. 
  - use contains('className') method to check if the classList has specific class 
```javascript
'use strict';

const modal = document.querySelector('.modal');
const overlay = document.querySelector('.overlay');
const btnCloseModal = document.querySelector('.close-modal');
const btnsOpenModal = document.querySelectorAll('.show-modal');

for (let i = 0; i < btnsOpenModal.length; ++i) {
  btnsOpenModal[i].addEventListener('click', () => {
    modal.classList.remove('hidden');
    overlay.classList.remove('hidden');
    console.log(modal.classList);
  });
}

```
- **Every CSS property are camel case in DOM methods**, So you should remove hyphen and change that property into the camel case.
- when you **change CSS sytle uisng (some element Selected by selector).style.color = "value";** all the property value in javascript should be wrapped with "" so it would be the string

### Changing Styles
- **style.{property} //ok**
- **getAttribute**
- **setAttribute**




## Manipulating Text
- **😱😱innerHTML(Dangerous) vs textContent** 
  - innerHTML returns the literally all the written things inside an selected element 
  - textContent returns only text of an selected element
  - 🔥**Warning!!** **input** elements use a **value property** to access it's text input data!!! 
- **Manipulating attribute of an HTML element**
  - you can get **array of attributes of an element using .attributes;**
  - you can see **specific attribute using .getAttribute('attribute name');**
  - change attribute **.setAttribute('Attribute you are going to change', 'what you are going to change it to');**
  
- When it comes to manipulating text in **input tag** we should **use value property**
  
## Control the Event
- Make your web to react to the ⭐event
- addEventListener(type, function) through this code you can add function to be called when listeners listen to the specific type **behavior(Event)**
- you can use debugger; in chrome developer tool
- We can **pass the event that trigers eventListener as a parameter to the function associated with the event listener**
- it's also possible for the entire web page to listen(wait for) to the event.(use document)
```javascript
      document.addEventListener('keydown',function(event){
        console.log(event);
      });
```

### Accessing parentElement and children
Element.parentElement
Element.children

It is important to CACHE selectors in variables.
- doesn't have to look up the DOM 
