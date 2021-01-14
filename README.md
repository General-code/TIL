# TIL
**Today I learned**


## About Front-end Programming Design
2020.11.18
[Manage ATTENTION with effective User Interface](https://github.com/General-code/TIL/blob/main/Front-end%20Design%20Princple.md)


## ISSUES
🤷‍♂️🤷‍♀️ Wihle I am coding at sparta I suddenly encountered some erros related with Bootstrap
  - [x] I used combination of grid and card but some errors occured. There should've been 4 cards in a line when the view-port was desktop-size and 2 cards in a line when the view-port was smaller. but the size of first card was different!!!😱😱 
    - use meta tag viewport
  - [x] Bootstrap, CSS, and other media sources didn't exist on the webpage from my localhost flask server. And Tutor Chan Ho Lee helped me to find out the cause of that error. It was casued from the flask's folder structure. I didn't placed css code and media files in the static folder. And After I **moved them from template directory to the static file directory. Everything was clear** 

- I suffered from some issues with forwarding a little information when I request for some informations rendering other HTMLfile. But It was resolved by using request's library. 
  > ex 
  
  ```python
    title = request.args.get('title')
    return render_template('show.html',title=title)
  ```
- When I was making a vanila javascript modal **I was stuck in removing class in the classList.** But after a minute I realized that I should pass only **pure text without any symbols indicating class**(cause this is classList we don't have to concern about it!)
## Javascript

### [Javascript DOM Manipulation](https://github.com/General-code/TIL/blob/main/Javascript%20DOM%20manipulation.md)


### [Javascript Object and Functions](https://github.com/General-code/TIL/blob/main/Javascript/Javascript%20Object%20and%20Functions.md)


### Javascript Variables Delcaration
- **let** has block level scope
- **var** has function level scope and can be redeclared. This should be completely avoided. It's scope level is so weird.
- ⭐**const** means that **the identifier can’t be reassigned.** (Not to be confused with immutable values. Unlike true immutable datatypes such as those produced by Immutable.js and Mori, a `const` object can have properties mutated.) 
- **should be initiallized with an declaration.**

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
  - when array becomes string with + then it concatenate every element with .(dot)

- **Truthy value and Falsy value**
  - Falsy values are undefined, 0, '', null, false



#### [Javascript Array](https://github.com/General-code/TIL/blob/main/JavascriptArray.md)
#### [Javascript Loop](https://github.com/General-code/TIL/blob/main/loop.js)
### [Javascript Engine](https://github.com/General-code/TIL/blob/main/Javascript/Javascript%20Engine.md)

### Animation 
- To use Animation first add the effect and then use **setTimeout(function(){}, milisec)** to remove it then it will work like an animation



## Node.js and npm
- **Node** liberate javascript language so it can be used on the backend. 
  - parseFloat is more safe than Number cause it only find number in string and return it.
- **NPM** is Node Package Manager install libraries and deal with dependencies
  - When you make package.json file to manage your project related inforamation because of the depndency of packages. [For more detailed information](https://docs.npmjs.com/cli/v6/configuring-npm/package-json).
  - The entry should be the main javascript file.
  - -g means global 
  
- **express** library is bulit for HTTP communication.
  - you can send HTML FILE with this method sendFILE( __dirName + 'index.html')
  - through the use function can use the other packages.
  - bodyParser parse the data from the http request.
```javascript
// jshint esversion:6
const express = require('express');
const bodyParser = require('body-parser');

const app = express();
app.use(bodyParser.urlencoded({extended: true}));

app.get('/', function (req, res) {
  res.sendFile(__dirname + '/index.html');
});

app.post('/', function (req, res) {
  let num1 = Number(req.body.num1);
  let num2 = Number(req.body.num2);

  let result = num1 + num2;
  res.send('The result of the calculation is ' + result);
});

app.listen(3000, function () {
  console.log('Server is running on port 3000.');
});
```

## API
- what is an API and what is it composed of?
- Application Programming Interface which is set of functions, data, objects and protocol.
  - Allow external server to use it's program
- Endpoint(the starting url of an API)
- Path used to for specific server
- Parameter used to narrow down on the data(to get specific data).
  - when used in url we can add like this ?varname='value'&varname2='value2'
- Authentication

## NETWORK 
- What happens when we hit the name of the internet service on our browser's url box? 
> then we asks question who is the {name} to the ISP(Internet Service Provider) and ISP requests the address of this name to the DNS(Domain name server)
and then DNS send off that request(IP address) back through the ISP to the web browser or website and our browser send requsts for that IP and get the respond end up with several files(HTML CSS JAVASCRIPT and the ohter things)
- Everything on the internet has it's own IP address (we're going to say about NAT later)
**Through the IP Address we can find the destination**
### INTERNET BACKBONE
  - When we use the WIFI in our home wifi is available through the router and that is connected to the Modem(we get this when we sign up internet service) which is connected to the ISP, to say somehting about backbone. everything is connected with the cables. you can see the cables connects every country under water

- Use **tracert** to trace hole bunch of hops and the destination IP address.
```shell
tracert google.com
```
