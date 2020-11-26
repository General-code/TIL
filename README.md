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

- I suffered from some issues with forwarding a little information when I request for some informations rendering other HTMLfile. But It is resolved by using request's library. 
  - ex 
  
  ```python
    title = request.args.get('title')
    return render_template('show.html',title=title)
  ```
