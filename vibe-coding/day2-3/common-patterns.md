# Common Coding Patterns

Reusable code patterns you'll likely need during Day 2-3. Copy, modify, and use these as needed!

---

## 📋 Working with Lists/Arrays

### Display a List of Items
```html
<!-- HTML -->
<ul id="itemList"></ul>
```

```javascript
// JavaScript
const items = ['Item 1', 'Item 2', 'Item 3'];
const listElement = document.getElementById('itemList');

function displayItems() {
  listElement.innerHTML = '';
  items.forEach(item => {
    const li = document.createElement('li');
    li.textContent = item;
    listElement.appendChild(li);
  });
}

displayItems();
```

### Add Item to List
```javascript
function addItem(newItem) {
  items.push(newItem);
  displayItems(); // refresh the display
}
```

### Remove Item from List
```javascript
function removeItem(index) {
  items.splice(index, 1);
  displayItems(); // refresh the display
}
```

### Filter/Search Items
```javascript
function searchItems(searchTerm) {
  const filtered = items.filter(item =>
    item.toLowerCase().includes(searchTerm.toLowerCase())
  );
  return filtered;
}
```

---

## 💾 Saving Data (localStorage)

### Save Data
```javascript
// Save array/object
const myData = [{ name: 'John', age: 30 }];
localStorage.setItem('myDataKey', JSON.stringify(myData));

// Save simple string
localStorage.setItem('username', 'John');
```

### Load Data
```javascript
// Load array/object
const loadedData = JSON.parse(localStorage.getItem('myDataKey')) || [];

// Load simple string
const username = localStorage.getItem('username') || 'Guest';
```

### Delete Data
```javascript
localStorage.removeItem('myDataKey');

// Or clear everything
localStorage.clear();
```

### Complete Save/Load Pattern
```javascript
const STORAGE_KEY = 'myAppData';

// Save
function saveData(data) {
  localStorage.setItem(STORAGE_KEY, JSON.stringify(data));
}

// Load
function loadData() {
  const data = localStorage.getItem(STORAGE_KEY);
  return data ? JSON.parse(data) : [];
}

// Usage
let myData = loadData(); // Load on startup
myData.push(newItem);    // Modify data
saveData(myData);        // Save changes
```

---

## 📝 Forms and Input

### Get Form Data
```html
<form id="myForm">
  <input type="text" id="name" required>
  <input type="email" id="email" required>
  <button type="submit">Submit</button>
</form>
```

```javascript
const form = document.getElementById('myForm');

form.addEventListener('submit', (e) => {
  e.preventDefault(); // Prevent page reload

  const name = document.getElementById('name').value;
  const email = document.getElementById('email').value;

  // Do something with the data
  console.log({ name, email });

  // Clear form
  form.reset();
});
```

### Form Validation
```javascript
function validateForm() {
  const name = document.getElementById('name').value.trim();
  const email = document.getElementById('email').value.trim();

  if (name === '') {
    alert('Name is required');
    return false;
  }

  if (!email.includes('@')) {
    alert('Invalid email');
    return false;
  }

  return true;
}

form.addEventListener('submit', (e) => {
  e.preventDefault();

  if (validateForm()) {
    // Process form
  }
});
```

---

## 🎛️ Buttons and Click Events

### Basic Button Click
```html
<button id="myButton">Click Me</button>
```

```javascript
document.getElementById('myButton').addEventListener('click', () => {
  console.log('Button clicked!');
});
```

### Dynamic Buttons (e.g., delete buttons)
```javascript
function displayItemsWithDelete() {
  listElement.innerHTML = '';

  items.forEach((item, index) => {
    const li = document.createElement('li');
    li.textContent = item;

    const deleteBtn = document.createElement('button');
    deleteBtn.textContent = 'Delete';
    deleteBtn.addEventListener('click', () => {
      removeItem(index);
    });

    li.appendChild(deleteBtn);
    listElement.appendChild(li);
  });
}
```

---

## 🔄 Show/Hide Elements

### Toggle Visibility
```javascript
function toggleElement(elementId) {
  const element = document.getElementById(elementId);

  if (element.style.display === 'none') {
    element.style.display = 'block';
  } else {
    element.style.display = 'none';
  }
}
```

### Show Success/Error Messages
```html
<div id="message" style="display: none;"></div>
```

```javascript
function showMessage(text, type = 'success') {
  const messageEl = document.getElementById('message');
  messageEl.textContent = text;
  messageEl.className = type; // 'success' or 'error'
  messageEl.style.display = 'block';

  // Hide after 3 seconds
  setTimeout(() => {
    messageEl.style.display = 'none';
  }, 3000);
}

// Usage
showMessage('Data saved!', 'success');
showMessage('Error occurred!', 'error');
```

---

## 📅 Working with Dates

### Get Current Date
```javascript
const now = new Date();
const dateString = now.toLocaleDateString(); // "10/7/2025"
const timeString = now.toLocaleTimeString(); // "2:30:00 PM"
```

### Format Date
```javascript
function formatDate(date) {
  const d = new Date(date);
  const year = d.getFullYear();
  const month = String(d.getMonth() + 1).padStart(2, '0');
  const day = String(d.getDate()).padStart(2, '0');
  return `${year}-${month}-${day}`; // "2025-10-07"
}
```

### Get Date Input Value
```html
<input type="date" id="dateInput">
```

```javascript
const dateValue = document.getElementById('dateInput').value;
// Returns: "2025-10-07"
```

---

## 🔢 Working with Numbers

### Parse User Input
```javascript
const userInput = document.getElementById('numberInput').value;
const number = parseFloat(userInput);

if (isNaN(number)) {
  alert('Please enter a valid number');
} else {
  console.log(number);
}
```

### Format Numbers
```javascript
const price = 1234.56;

// Currency
price.toFixed(2); // "1234.56"

// Thousands separator
price.toLocaleString(); // "1,234.56"
```

### Calculate Total
```javascript
const items = [
  { name: 'Item 1', price: 10 },
  { name: 'Item 2', price: 20 },
  { name: 'Item 3', price: 15 }
];

const total = items.reduce((sum, item) => sum + item.price, 0);
console.log(total); // 45
```

---

## 🎨 Styling and Classes

### Add/Remove CSS Classes
```javascript
const element = document.getElementById('myElement');

// Add class
element.classList.add('active');

// Remove class
element.classList.remove('active');

// Toggle class
element.classList.toggle('active');

// Check if has class
if (element.classList.contains('active')) {
  console.log('Element is active');
}
```

### Change Inline Styles
```javascript
const element = document.getElementById('myElement');

element.style.color = 'red';
element.style.backgroundColor = 'blue';
element.style.display = 'none';
```

---

## 📊 Filtering and Sorting

### Filter Array by Condition
```javascript
const numbers = [1, 2, 3, 4, 5, 6];

// Get only even numbers
const even = numbers.filter(n => n % 2 === 0);
// [2, 4, 6]

// Filter objects
const people = [
  { name: 'John', age: 30 },
  { name: 'Jane', age: 25 },
  { name: 'Bob', age: 35 }
];

const over30 = people.filter(person => person.age > 30);
// [{ name: 'Bob', age: 35 }]
```

### Sort Array
```javascript
// Sort numbers ascending
const numbers = [3, 1, 4, 1, 5];
numbers.sort((a, b) => a - b);
// [1, 1, 3, 4, 5]

// Sort numbers descending
numbers.sort((a, b) => b - a);
// [5, 4, 3, 1, 1]

// Sort objects by property
const people = [
  { name: 'John', age: 30 },
  { name: 'Jane', age: 25 }
];

people.sort((a, b) => a.age - b.age); // Sort by age
```

---

## 🔍 Search Functionality

### Simple Search
```html
<input type="text" id="searchInput" placeholder="Search...">
<ul id="results"></ul>
```

```javascript
const allItems = ['Apple', 'Banana', 'Orange', 'Grape'];
const searchInput = document.getElementById('searchInput');
const resultsEl = document.getElementById('results');

searchInput.addEventListener('input', (e) => {
  const searchTerm = e.target.value.toLowerCase();

  const filtered = allItems.filter(item =>
    item.toLowerCase().includes(searchTerm)
  );

  displayResults(filtered);
});

function displayResults(items) {
  resultsEl.innerHTML = '';
  items.forEach(item => {
    const li = document.createElement('li');
    li.textContent = item;
    resultsEl.appendChild(li);
  });
}
```

---

## 📋 Copying to Clipboard

```javascript
function copyToClipboard(text) {
  navigator.clipboard.writeText(text)
    .then(() => {
      showMessage('Copied to clipboard!');
    })
    .catch(err => {
      console.error('Failed to copy:', err);
    });
}

// Usage
document.getElementById('copyBtn').addEventListener('click', () => {
  copyToClipboard('Text to copy');
});
```

---

## 📥 File Upload

```html
<input type="file" id="fileInput" accept="image/*">
```

```javascript
document.getElementById('fileInput').addEventListener('change', (e) => {
  const file = e.target.files[0];

  if (file) {
    console.log('File name:', file.name);
    console.log('File size:', file.size);
    console.log('File type:', file.type);

    // Read file as text
    const reader = new FileReader();
    reader.onload = (e) => {
      const content = e.target.result;
      console.log('File content:', content);
    };
    reader.readAsText(file);
  }
});
```

---

## 🎲 Generating IDs

### Simple Unique ID
```javascript
function generateId() {
  return Date.now().toString(36) + Math.random().toString(36).substr(2);
}

// Usage
const newItem = {
  id: generateId(),
  name: 'Item name',
  // ... other properties
};
```

---

## 📦 Complete Example: Todo List

Putting it all together:

```html
<!DOCTYPE html>
<html>
<head>
  <title>Todo List</title>
  <style>
    .completed { text-decoration: line-through; }
  </style>
</head>
<body>
  <input type="text" id="todoInput" placeholder="Add todo...">
  <button id="addBtn">Add</button>
  <ul id="todoList"></ul>

  <script>
    const STORAGE_KEY = 'todos';
    let todos = loadTodos();

    function loadTodos() {
      const data = localStorage.getItem(STORAGE_KEY);
      return data ? JSON.parse(data) : [];
    }

    function saveTodos() {
      localStorage.setItem(STORAGE_KEY, JSON.stringify(todos));
    }

    function displayTodos() {
      const list = document.getElementById('todoList');
      list.innerHTML = '';

      todos.forEach((todo, index) => {
        const li = document.createElement('li');
        li.textContent = todo.text;
        if (todo.completed) {
          li.classList.add('completed');
        }

        // Toggle complete
        li.addEventListener('click', () => {
          todos[index].completed = !todos[index].completed;
          saveTodos();
          displayTodos();
        });

        // Delete button
        const deleteBtn = document.createElement('button');
        deleteBtn.textContent = 'Delete';
        deleteBtn.addEventListener('click', (e) => {
          e.stopPropagation(); // Don't trigger li click
          todos.splice(index, 1);
          saveTodos();
          displayTodos();
        });

        li.appendChild(deleteBtn);
        list.appendChild(li);
      });
    }

    document.getElementById('addBtn').addEventListener('click', () => {
      const input = document.getElementById('todoInput');
      const text = input.value.trim();

      if (text) {
        todos.push({ text, completed: false });
        saveTodos();
        displayTodos();
        input.value = '';
      }
    });

    // Load on startup
    displayTodos();
  </script>
</body>
</html>
```

---

## 💡 How to Use These Patterns

1. **Copy the code** that matches what you need
2. **Modify** variable names and logic for your use case
3. **Ask AI** to help adapt it if needed
4. **Test** to make sure it works
5. **Build upon it** - combine patterns as needed

**Remember:** You don't need to memorize this - just reference it when building!
