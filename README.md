# DOM Manipulation & Event Propagation Assignment

## Project Overview

This project is a simple Task Manager application built using HTML, CSS, and JavaScript. Users can add, edit, complete, and delete tasks. The project also demonstrates Event Bubbling, Event Capturing, Event Delegation, and the Browser Rendering Pipeline.

---

## Browser Rendering Pipeline

When a browser loads a webpage, it follows several steps before displaying the content on the screen.

### 1. Parsing

Parsing is the process of reading HTML and CSS files. The browser goes through the code line by line and tries to understand the structure of the page.

Example:

```html
<h1>Hello World</h1>
```

The browser reads this code and recognizes that it is a heading element.

### 2. Tokenization

During tokenization, the browser breaks the HTML into smaller pieces called tokens.

Example:

```html
<h1>Hello World</h1>
```

The browser identifies:

* Opening tag: `<h1>`
* Text content: `Hello World`
* Closing tag: `</h1>`

These tokens help the browser understand the document structure.

### 3. DOM Tree

After parsing and tokenization, the browser creates a DOM (Document Object Model) Tree.

The DOM Tree represents all HTML elements as objects connected in a tree structure.

Example:

```text
Document
 └── html
      └── body
           └── h1
```

JavaScript uses the DOM Tree to access and modify page content.

### 4. CSSOM Tree

The browser also parses CSS and creates a CSSOM (CSS Object Model) Tree.

The CSSOM contains all styling information for the webpage.

Example:

```css
h1 {
    color: blue;
}
```

The browser stores this style information in the CSSOM Tree.

### 5. Render Tree

The Render Tree is created by combining:

* DOM Tree
* CSSOM Tree

The browser uses the Render Tree to determine what should appear on the screen and how it should look.

After the Render Tree is created, the browser paints the page for the user.

---

## Event Bubbling

Event Bubbling is the default event behavior in JavaScript.

When an event occurs on a child element, it first runs on that element and then moves upward through its parent elements.

Example:

```text
Child
Parent
Grandparent
```

If a button is clicked inside a parent container, the event will travel from the button to the parent and then to the grandparent.

---

## Event Capturing

Event Capturing works in the opposite direction.

The event starts from the outermost parent and travels down to the target element.

Example:

```text
Grandparent
Parent
Child
```

Capturing is enabled by passing `true` or `{ capture: true }` as the third parameter of `addEventListener()`.

---

## Event Delegation

Event Delegation is a technique where a single event listener is attached to a parent element instead of multiple child elements.

In this project, event delegation is used to handle Edit, Delete, and Complete button clicks.

Example:

```javascript
taskList.addEventListener('click', (event) => {
    if (event.target.classList.contains('deleteBtn')) {
        // Delete task
    }
});
```

Benefits of Event Delegation:

* Better performance
* Less code
* Works for dynamically created elements
* Easier to maintain

---

## Features Implemented

* Add Task
* Edit Task
* Delete Task
* Complete Task
* Category Selection
* Event Bubbling Demonstration
* Event Capturing Demonstration
* Browser Rendering Pipeline Visualization
* Event Delegation

---

## Technologies Used

* HTML5
* CSS3
* JavaScript (ES6)

---

## How to Run

1. Download or clone the repository.
2. Open the project folder.
3. Open `index.html` in a browser.
4. Start using the application.

---

## Author

Created as part of a JavaScript DOM Manipulation and Event Propagation assignment.
