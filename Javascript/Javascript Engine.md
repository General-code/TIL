### Javascript Engine
- Any Javascript Engine always contains a call stack and a heap
 - ![javascript memory model](https://blog.kakaocdn.net/dn/bAGG5c/btqChFytmpg/qLtzgp3ahZgqkcIlD9mtkK/img.png)
 - **call stack is where our code is excuted** using something called **excution context** and **heap is an unstructured memory pool** which **stores all the objects** that aour application needs.
 
#### Steps
- javascript was a interpreted language, but this is not true anymore.
- but now it's diffrent. Because Javascript support Just In Time compilation
- JIT compiler convert source code to machine code and don't make any portable file, just immediately excute them.

1. first **javascript code is parsed into the data structrue called AST**(Abstract syntax tree)
  - This works by first **splitting up eaxh line of code into pieces that are meaningful to the language** such as const or function keyword.
  - each pieces of codes are saved into the tree in a structured way.
  - This step also **cehcks if there are any syntax error**s and the **resulting tree will later be used to generate the machine code**
 
2. The AST is just representation of entire code into the engine.
  - the next step is compilation. This process takes the generated AST and compiles it into machine code.
  - This machine code just excuted right away because javascript engine uses JIT(Just in time) compilation.
  - Remeber **Execution happens in the javascript engines call stack**.
  - for more deep informaation visit this site(https://medium.com/@zoebai_70369/javascript-engine-368037453a1c)
  
3. Javscript Optimization strategies
  -  create very unoptimized version of machine code in the beginning just so that it can start executing as fast as possible.
  -  Then in the background this code is being optimized and recompiled during the already running program execution.
  - and this can be done most of time and after each optimization the unoptimized code is simply swept for the new more optimized code without ever stopping execution of codes.
  - ⭐All this parsing, compilation, Optimization happends in some special threads inside the engine that we can not access from our code.This is copmpleted diffrent from main thread
  
### Javscript Runtime 
- made of JS ENGINE And WEB APIs(not the part of javascript), javscript access WEB APIs through the global window object. but web APIs also be a part of javascript runtime as javascript runtime contains all the javascript related things that we need.
- **CALLBACK QUEUE** is also needed to javascript runtime. Callback queue is a datastructure that contians all the callback functions that are ready to be excuted.
> FOR example we attach event handler functinos to DOM element like a button to react to certain event, And this event functions are also called callback functions. As the event happen, for example a click, the callback function will be called.
- First when the callback function is called, the callback function is put into the callback queue, then when the call stack is empty the callback function is passed to the stack so that it can be executed. And this happens by something called event loop.
![Figure of Runtime](https://cdn-images-1.medium.com/max/1600/1*lZ-KXoVNUSOwaq7q8zUBDg.png)

- But in nodes Js things are different. cause node js in not a browser, It don't provide WEB APIs but C++ Bindings and thread pool
