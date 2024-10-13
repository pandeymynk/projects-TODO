# Todo List Application

This is a simple Todo List application built using HTML, CSS, and JavaScript. The application allows users to add tasks and mark them as completed by clicking on them.

## Table of Contents
1. [HTML Structure](#html-structure)
2. [CSS](#css)
3. [JavaScript](#javascript)
4. [How It Works](#how-it-works)

---

## HTML Structure

The HTML file is the basic structure of your Todo List. Below is the explanation of the important tags used in the code:

### `<!DOCTYPE html>`
- This tag declares the document type and version of HTML (HTML5 in this case).

### `<html lang="en">`
- This tag is the root element of the HTML document. The `lang` attribute specifies the language of the document, which is set to "English" (`en`).

### `<head>`
- Contains metadata and external links for the document.
- Inside the `<head>`, we have:
  - `<meta charset="UTF-8">`: Specifies the character encoding of the document, ensuring that characters display correctly.
  - `<meta name="viewport" content="width=device-width, initial-scale=1.0">`: Ensures the page is responsive and adjusts correctly to different screen sizes.
  - `<title>Document</title>`: Sets the title of the web page, which appears on the browser tab.
  
### `<body>`
- Contains the content of the web page that users see and interact with.
- Inside the `<body>`, we have:
  - `<div>`: A container that holds the main elements (input and list).
    - `<input type="text" id="write">`: This is an input field where the user types a todo item. The `id="write"` is used to reference this element in JavaScript.
    - `<ul id="todo-list" style="list-style-type: none;">`: This is an unordered list (`<ul>`) where the todo items will be added. The `style="list-style-type: none;"` removes the default bullet points from the list.

---

## CSS

CSS is used to style the elements and provide visual cues to the user. In this case, we use a simple style to mark completed tasks.

### `.done`
- A CSS class applied to a task when it is marked as "done" (completed). It uses `text-decoration: line-through;` to cross out the text when the task is completed.

---

## JavaScript

The JavaScript code handles the functionality of the Todo List, such as adding new tasks and marking tasks as completed.

### `let write = document.getElementById("write");`
- This line fetches the input field with `id="write"` and stores it in a variable `write`. We can use this variable to interact with the input field.

### `let todolist = document.getElementById('todo-list');`
- This line fetches the unordered list (`<ul>`) where the todo items will be displayed.

### `write.addEventListener("keyup", function(e) {...});`
- Adds an event listener to the input field, which listens for when the user presses a key. Specifically, it checks if the key pressed is the "Enter" key.

  - `if (e.key == "Enter") {...}`: Inside the event listener, we check if the pressed key is the "Enter" key. If true, the `addTodo()` function is called, passing the value of the input field (`this.value`) as an argument. This adds the new todo item to the list. After adding, the input field is cleared (`this.value = '';`).

### `function addTodo(val) {...}`
- This function takes the value from the input field (`val`) and creates a new `<li>` (list item) element in the todo list.

  - `let list = document.createElement("li");`: Creates a new `<li>` element.
  - `list.innerHTML = \`${val}\`;`: Sets the inner HTML of the new `<li>` to the value passed (the task entered by the user).
  - `todolist.appendChild(list);`: Adds the new `<li>` element to the `<ul>` (todo list).
  - `list.addEventListener("click", function() {...});`: Adds an event listener to the newly created `<li>` element. When the user clicks on a task, the class `done` is toggled, which crosses out the task.

---

## How It Works

1. **Adding a Task**: 
   - The user types a task in the input field.
   - When the "Enter" key is pressed, the task is added to the list (`<ul>`) as a new `<li>` element.
   
2. **Marking a Task as Done**: 
   - When the user clicks on a task in the list, the JavaScript code toggles the class `done` on that task.
   - The `done` class applies the `text-decoration: line-through` style, visually indicating that the task is completed.

---

## Conclusion

This Todo List application is a simple example of using HTML, CSS, and JavaScript together to create a functional and interactive webpage. You can enhance it by adding more features like task deletion, task editing, or even persisting the list in local storage so the tasks remain after refreshing the page.
