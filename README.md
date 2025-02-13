# **DOM Manipulation Notes**

## **1. Understanding `innerHTML`, `innerText`, and `textContent`**

When working with the DOM, `innerHTML`, `innerText`, and `textContent` are used to change or retrieve the content inside an element. However, they have key differences:

### **Differences:**

1. **`innerHTML`**
   - Allows setting or retrieving HTML content inside an element.
   - Parses any HTML tags included in the string.

   **HTML:**
   ```html
   <div id="example"></div>
   ```
   
   **JavaScript:**
   ```javascript
   let div = document.getElementById("example");
   div.innerHTML = "<strong>Hello, World!</strong>"; // Renders as bold text
   ```

2. **`innerText`**
   - Retrieves or sets only the visible text inside an element.
   - Ignores hidden elements (e.g., `display: none`).
   - Does **not** process HTML tags as markup.

   **JavaScript:**
   ```javascript
   let div = document.getElementById("example");
   div.innerText = "<strong>Hello, World!</strong>"; // Displays raw text, not bold
   ```

3. **`textContent`**
   - Similar to `innerText`, but retrieves all text, including hidden content.
   - Does **not** parse HTML tags.

   **JavaScript:**
   ```javascript
   let div = document.getElementById("example");
   div.textContent = "<strong>Hello, World!</strong>"; // Displays as raw text
   ```

---

## **2. Important DOM Properties**

1. **`document.body`**
   - Accesses the `<body>` element of the document.

   **JavaScript:**
   ```javascript
   console.log(document.body);
   ```

2. **`document.forms`**
   - Returns a collection of all `<form>` elements in the document.

   **JavaScript:**
   ```javascript
   console.log(document.forms);
   ```

3. **`document.images`**
   - Returns a collection of all `<img>` elements in the document.

   **JavaScript:**
   ```javascript
   console.log(document.images);
   ```

4. **`document.title`**
   - Gets or sets the title of the document.

   **JavaScript:**
   ```javascript
   console.log(document.title);
   document.title = "New Page Title";
   ```

5. **`document.links`**
   - Returns a collection of all `<a>` elements with an `href` attribute.

   **JavaScript:**
   ```javascript
   console.log(document.links);
   ```

---

## **3. Common DOM Methods**

### **Selecting Elements**

1. **`getElementsByTagName(tagName)`**
   - Returns a collection of elements with the specified tag name.

   **HTML:**
   ```html
   <p>Paragraph 1</p>
   <p>Paragraph 2</p>
   ```

   **JavaScript:**
   ```javascript
   let paragraphs = document.getElementsByTagName("p");
   console.log(paragraphs);
   ```

2. **`getElementsByClassName(className)`**
   - Returns a collection of elements with the specified class name.

   **HTML:**
   ```html
   <div class="item">Item 1</div>
   <div class="item">Item 2</div>
   ```
   
   **JavaScript:**
   ```javascript
   let items = document.getElementsByClassName("item");
   console.log(items);
   ```

3. **`querySelector(selector)`**
   - Returns the **first** element that matches a CSS selector.

   **JavaScript:**
   ```javascript
   let firstItem = document.querySelector(".item");
   console.log(firstItem);
   ```

4. **`querySelectorAll(selector)`**
   - Returns a **NodeList** of all elements that match a CSS selector.

   **JavaScript:**
   ```javascript
   let allItems = document.querySelectorAll(".item");
   console.log(allItems);
   ```

5. **`getElementById(id)`**
   - Returns the element with the specified ID.

   **HTML:**
   ```html
   <h1 id="header">Hello</h1>
   ```
   
   **JavaScript:**
   ```javascript
   let header = document.getElementById("header");
   console.log(header);
   ```

---

## **4. Modifying Content of an Element**

### **Using `innerHTML`, `innerText`, and `textContent`**

**HTML:**
```html
<div id="content"></div>
```

**JavaScript:**
```javascript
let element = document.getElementById("content");
element.innerHTML = "<h1>Welcome</h1>"; // Injects an h1 element
```

---

## **5. Creating and Appending Elements**

### **Creating a New Element**

**JavaScript:**
```javascript
let newDiv = document.createElement("div");
newDiv.textContent = "This is a new div.";
```

### **Appending a Child to a Parent Element**

**HTML:**
```html
<div id="container"></div>
```

**JavaScript:**
```javascript
let parent = document.getElementById("container");
parent.appendChild(newDiv);
```

This ensures the new `<div>` is added as a child inside the `#container` element.

---

### **Summary**

- Use `innerHTML` for inserting HTML, `innerText` for visible text, and `textContent` for all text (including hidden ones).
- `document.body`, `document.forms`, `document.images`, `document.title`, and `document.links` provide quick access to document elements.
- `getElementsByTagName`, `getElementsByClassName`, `querySelector`, `querySelectorAll`, and `getElementById` allow you to select elements effectively.
- `document.createElement` and `appendChild` help dynamically create and insert elements into the DOM.

By mastering these DOM manipulation techniques, you'll be able to build dynamic, interactive web pages efficiently!

