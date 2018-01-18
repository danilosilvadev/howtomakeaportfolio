# FRONTEND
If you are new at development and don't know what to do to demonstrate your skills, this repo is to you :D

## How this works?

This repo gives ideas to small apps that can show different fields of basic programming to create your initial portolio. Also shows how to create those apps and where to find the knowledge enough to do it. ENJOY!


## Table of Contents

#### Frontend

I assume that you already have basic knowledge in basic (html, css and js). Frontend development you will need to demonstrate your skills with:

- [CSS technologies](#CSS)
  - CSS3
  - Responsivity
  - Bootstrap
  - Layout Systems
  - Pre-processors
- [JavaScrip](#Javascript)
  - DOM
  - AJAX
  - es2015
  - CRUD
  - API consuming
  - jQuery
  - Design Patterns/important JS features
  - Frontend frameworks(optional)
  
*PS: Each topic of this repo has several options, so you can choose wich one fits your goal with coding.*

### Backend

Needs data here.

# Frontend

### <a name="CSS">CSS</a>

 To create some interesting css projects you can dig into some important aspects of css beyond basics, that they are:

 1. CSS3
- Where to learn: [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS3).
- Small examples: [Submarine](https://codepen.io/ajerez/pen/EaEEOW), [Loader](https://codepen.io/Bidji/pen/dPEzwq) and [Star Wars](https://codepen.io/donovanh/pen/pJzwEw).
- What you can do: You could do a simple draw with some animation or make some buttons with [transitions effects](https://www.webdesignerdepot.com/2014/05/8-simple-css3-transitions-that-will-wow-your-users/).
2. Responsivity
- Where to learn: [W3schools](https://www.w3schools.com/css/css_rwd_intro.asp), [mobile first](https://developer.mozilla.org/en-US/Apps/Progressive/Responsive/Mobile_first) and [more mdn](https://developer.mozilla.org/en-US/Apps/Progressive/Responsive/responsive_design_building_blocks).
- Small examples: 
- What you can do:
- Sample: https://gist.github.com/danilosilvadev/3713b11f123b6387b2dc2cbb60794eaf
3. Bootstrap
- Where to learn: [GetBootstrap](https://getbootstrap.com/docs/4.0/getting-started/introduction/).
- Small examples: [simple examples](https://tutorialzine.com/2015/06/12-time-saving-bootstrap-examples).
- What you can do: You can do a responsive page using bootstrap col-system with 3 different components of bootstrap.
4. Layout systems (flexbox and grid)
- Where to learn: [Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) and [GRID](https://css-tricks.com/snippets/css/complete-guide-grid/).
- Small examples:
- What you can do: You can create a page a little more complex layout with several columns and responsive to not just phones but also tablets.
- Sample: 
![Demo](https://media.giphy.com/media/3ohjV6uMN53tgrAs12/giphy.gif)
https://codepen.io/danilosilvadev/pen/ZvmKyj
5. Pre-processors (sass or less)
- Where to learn: [Sass](http://sass-lang.com/guide) and [Less](http://lesscss.org/).
- Small examples:
- What you can do: You can translate some of your older projects to sass or less and compare the difference between them and css.

### <a name="Javascript">Javascript</a>
 1. DOM
- Where to learn: [Mastering the DOM access](http://krasimirtsonev.com/blog/article/Mastering-the-DOM-access-JavaScript-set-get-value)and [W3Schools](https://www.w3schools.com/js/js_htmldom.asp).
- Small examples: [W3Schools examples](https://www.w3schools.com/js/js_dom_examples.asp).
- What you can do: You can create a form that sends data through the DOM and display the text inside a 'ul' list.
 2. AJAX requests
- Where to learn: [MDN](https://developer.mozilla.org/pt-BR/docs/AJAX) and [W3Schools](https://www.w3schools.com/js/js_ajax_intro.asp).
- Small examples: 
- What you can do: You can create a folder with 2 others folders inside it. Than create a file that has a dropdown menu where the options are the folders name(using ajax) and when clicked shows the content of the folder.
3. es2015
- Where to learn: [Babel](https://babeljs.io/learn-es2015/).
- Small examples: [devHints](https://devhints.io/es6).
- What you can do: You can convert your last examples to es2015 and compare how many lines you spared.
 4. CRUD
- Where to learn: [CRUD article](https://medium.com/@etiennerouzeaud/a-simple-crud-application-with-javascript-ebc82f688c59), [CRUD tutorial](https://www.codeproject.com/Articles/753724/JavaScript-Front-End-Web-App-Tutorial-Part) and [TodoList from W3School](https://www.w3schools.com/howto/howto_js_todolist.asp).
- Small examples: [Todolist on codepen](https://codepen.io/jagaranga/pen/FmdbL) and [Vanilla JS CRUD](https://codepen.io/bobby5develops/pen/QwJzQm).
- What you can do: Create a todolist and also a second list of the tasks setted to "done". Be creative, use css3 animations when the states changes!
- Sample:

TODO using DOM and es2015:

**HTML**

```html
<body>
    <h1>Simple Todo List</h1>

    Name:
    <input id="formAdd" type="text" name="name">
    <button onclick="add()">Add</button>
    </br>
    <div id="todoList">
        <ul id="list">

        </ul>
    </div>

    <script src="todo.js"></script>
</body>
```

**JS:**

```js
createLiElement = (value) => {
    const ul = document.getElementById("list");
    const li = document.createElement("li");
    const children = ul.children.length + 1;
    const buttonDelete = document.createElement("button");
    const buttonUpdate = document.createElement("button");
    buttonDelete.innerHTML = "Delete";
    buttonDelete.onclick = deleteBtn;
    buttonUpdate.innerHTML = "Update";
    document.getElementById("formAdd").value = '';
    buttonUpdate.onclick = (e, addEventListener) => updateBtn(closure(), e);
    li.setAttribute("id", children);
    const closure = () => {
        return {
            ul: ul,
            li: li,
            buttonDelete: buttonDelete,
            buttonUpdate: buttonUpdate
        }
    }
    li.appendChild(document.createTextNode(value + ' '));
    li.appendChild(buttonDelete);
    li.appendChild(buttonUpdate);
    ul.appendChild(li)
};

add = () => {
    const addValue = document.getElementById("formAdd").value;
    return (addValue === null || addValue === '') ? alert('Please fill this form') : createLiElement(addValue);
};

deleteBtn = (e) => {
    const liId = e.path[1].id;
    const elem = document.getElementById(liId);
    elem.parentNode.removeChild(elem);
};

updateBtn = (closure, e) => {
    const value = document.getElementById("formAdd").value;    
    return (value === null || value === '') ? alert('Write in the field!') : (() => {
        const liId = e.path[1].id;
        const elem = document.getElementById(liId);
        closure.buttonDelete.innerHTML = "Delete";
        closure.buttonDelete.onclick = deleteBtn;
        closure.buttonUpdate.innerHTML = "Update";
        const div = document.createElement("div");
        const item = closure.li.appendChild(div);
        item.setAttribute("id", liId);        
        div.appendChild(document.createTextNode(value + " "))
        div.appendChild(closure.buttonDelete);
        div.appendChild(closure.buttonUpdate);
        elem.parentNode.replaceChild(item, elem);
        document.getElementById("formAdd").value = '';      
        })();
};
```
4. API consuming
- Where to learn: Using [ajax](https://www.codecademy.com/pt-BR/tracks/parse), using [jquery](https://spring.io/guides/gs/consuming-rest-jquery/) or using [axios](https://github.com/axios/axios)(this one needs to know NPM and node modules manegement, it is optional to use this).
- Small examples:
- What you can do: You can make a search field that receives a string, and returns some information from some public API [here](https://github.com/toddmotto/public-apis).
- Sample:
```js
//This shows in the console random jokes about Chuck Norris.
(function loadDoc() {
      var xhttp = new XMLHttpRequest();
      xhttp.onreadystatechange = function() {
      if (this.readyState == 4 && this.status == 200) {
        var obj = JSON.parse(this.response);  //Parser to extract just the information that i want.
            console.log(obj.value.joke); 
        }
      };
      xhttp.open("GET", "http://api.icndb.com/jokes/random", false);
      xhttp.send();
    } )();
```
5.jQuery
- Where to learn: 
- Small examples: 
- What you can do: 
- Sample: The same todolist of the CRUD sample, but using jQuery instead of DOM.

```html
<html>
<head></head>
<body>
    <h1>Simple Todo List</h1>

    Name:
    <input id="formAdd" type="text" name="name">
    <button onclick="add()">Add</button>
    <br />
    <div id="todoList">
        <ul id="lista">

        </ul>
    </div>

    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
    <script src="jtest.js"></script>
</body>
</html>
```
```js
createLiElement = value => {
  const ul = $("#lista");
  const children = $("#lista li").length+1;
  const li = $("<li>").attr("id", children);
  const button = new buttons();
  button.buttonDelete.click(() => deleteBtn(button.buttonDelete));
  button.buttonUpdate.click(e => updateBtn(closure));
  const closure = {
    ul: ul,
    li: li,
    buttonDelete: button.buttonDelete,
    buttonUpdate: button.buttonUpdate
  }
  li.append(document.createTextNode(value + ' ')).append(button.buttonDelete).append(button.buttonUpdate);
  ul.append(li);
  $("#formAdd").val('');
};

buttons = function() {
  return {
    buttonDelete : $("<button>").text('delete'),
    buttonUpdate : $("<button>").text('update')
  }
};

add = () => {
  const addValue = $("#formAdd").val();
  return (addValue === null || addValue === '') ? alert('Please fill this form') : createLiElement(addValue);
};

deleteBtn = button => {
  button.parent().remove();
}

updateBtn = (closure) => {
  const value = $("#formAdd").val();
  return (value === null || value === '') ? alert('Write in the field!') : (() => {
    const itemOld = $('#'+closure.li.attr('id'));
    const itemNew = $('<li>').attr('id', closure.li.attr('id')).
    append(document.createTextNode(value + " ")).append(closure.buttonDelete).
    append(closure.buttonUpdate);
    itemOld.replaceWith(itemNew);
    $("#formAdd").val('');
  })();
};
```

6. Patterns and important JS features
- Where to learn: [MVC](https://addyosmani.com/resources/essentialjsdesignpatterns/book/#detailmvc), [closures and module pattern](https://medium.com/@danilosilvadev/a-tale-about-closures-js-58f5037b712d), types of [for loops](https://medium.com/@danilosilvadev/the-js-for-wer-rangers-never-more-use-the-classic-for-loop-de9f054014c3), [this](https://medium.com/@danilosilvadev/the-four-tests-of-this-in-js-technique-88a26346611c) and [singleton pattern](https://addyosmani.com/resources/essentialjsdesignpatterns/book/#singletonpatternjavascript).
- SmallExamples:
- What you can do:
- Samples:
Pagination example(this can be apply to blogs pages, sites of news and any site situation with lists in multiple pages) -
```js
// This is a pagination Sample:

// The constructor takes in an array of items and a integer indicating how many
// items fit within a single page
function PaginationHelper(collection, itemsPerPage){
  this.collection = collection, this.itemsPerPage = itemsPerPage;
}

// returns the number of items within the entire collection
PaginationHelper.prototype.itemCount = function() {
  return this.collection.length;
}

// returns the number of pages
PaginationHelper.prototype.pageCount = function() {
  return Math.floor(this.collection.length/this.itemsPerPage)+1;
}

// returns the number of items on the current page. page_index is zero based.
// this method should return -1 for pageIndex values that are out of range
PaginationHelper.prototype.pageItemCount = function(pageIndex) {
  return pageIndex > this.pageCount() - 1 || pageIndex < 0 ?
  -1 : pageIndex !== this.pageCount() - 1 ?
  this.itemsPerPage : this.collection.length -
  (this.itemsPerPage*this.pageCount())
  + this.itemsPerPage;
}

// determines what page an item is on. Zero based indexes
// this method should return -1 for itemIndex values that are out of range
PaginationHelper.prototype.pageIndex = function(itemIndex) {
  return itemIndex >= this.collection.length || itemIndex < 0 ?
  -1 : itemIndex === 0 ? 0 : Math.round(++itemIndex/helper.itemsPerPage);
}

var helper = new PaginationHelper(['1',2,3,4,5,'6',7,8,9,10,'11',12,13,14,15,'16',17,18,19,20,'21', 22], 5);
console.log(helper.pageItemCount(4));

//The same code but in another way, using scope strategy:

const PaginationHelper = (collection, itemsPerPage) => {
  this.collection = collection;
  this.itemsPerPage = itemsPerPage;
  this.itemCount = () => this.collection.length;
  this.pageCount = () => Math.ceil(this.collection.length / this.itemsPerPage);
  this.pageItemCount = idx => {
    this.pageCount() === ++idx ? this.itemCount() % this.itemsPerPage :
    this.pageCount() < ++idx ? -1 : this.itemsPerPage;
  };
  this.pageIndex = idx => {
    if (idx < 0) return -1;
    return ++idx > this.itemCount() ? -1 : ++idx === this.itemCount() ? this.pageCount() - 1 :
    idx / this.itemsPerPage ^ 0;
  }
}
```
7. Frameworks frontend
- Where to learn: [React](https://reactjs.org/docs/hello-world.html), [vue](https://vuejs.org/v2/guide/), [angular4](https://angular.io/docs), [jquery](https://learn.jquery.com/).
- Small examples:
- What you can do:

*PS: Site with todolists implemmented in several js frameworks: http://todomvc.com/*
