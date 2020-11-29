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

### Javascript DOM Manipulation(https://github.com/General-code/TIL/blob/main/Javascript%20DOM%20manipulation)


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




