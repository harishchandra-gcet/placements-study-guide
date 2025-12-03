# Practice Questions - HTML

## Q1

You are tasked with completing the functionality for a "Todo List" application. The application already has some basic functionality where a user can enter some text and add it to the Todo List, but several key pieces are missing or need completion.

### Objective(s):

1.  Add an **`<h1>`** tag at the top of the page with the text **"Todo List"**.
2.  Ensure that the cursor changes to a **pointer** when hovering over the buttons.
3.  Implement **delete functionality** so that when the **"Delete"** button is clicked, the corresponding task is removed from the list.

### Constraint(s):

  * Do not change the **"name"** or **"id"** of any element in the HTML as it will cause the code developed by the back-end developer to fail.
  * Do not remove the **CDN link for jQuery** as your code will not run without it.

-----

### `index.html`

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Todo List App</title>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
    <style>

    </style>
</head>
<body>
    <div>
        <input type="text" id="todo-input" placeholder="New task...">
        <button id="add-button" class="btn">Add</button>
    </div>

    <ul id="todo-list">
        <li class="todo-item">
            <span>Learn HTML</span>
            <button class="delete-button btn">Delete</button>
        </li>
        <li class="todo-item">
            <span>Practice SQL</span>
            <button class="delete-button btn">Delete</button>
        </li>
    </ul>

    <script>
        $(document).ready(function() {
                        $('#add-button').on('click', function() {
                var taskText = $('#todo-input').val();
                if (taskText !== "") {
                    var newTodo = '<li class="todo-item"><span>' + taskText + '</span> <button class="delete-button btn">Delete</button></li>';
                    $('#todo-list').append(newTodo);
                    $('#todo-input').val('');
                }
            });
        });
    </script>
</body>
</html>
```

---

## Q2

You are developing a **fruit chart** to help students learn fruit names. The chart contains a dropdown menu of fruit names, and after selecting any option from the menu the assigned fruit image is displayed. The chart is still in development and you need to complete the following objectives.

### Objective(s):

1.  Create a **select dropdown** of $\text{id}$ "**fruit-dropdown**" with three options of values: "**Apple**", "**Banana**", and "**Cherry**". The text inside these options will be apple, banana and cherry.
2.  Ensure the images have a **maximum width of 300px**.
3.  Complete the **switch cases in javascript** tab to properly align the correct fruit images with the correct option.

### Constraint(s):

* Do not change the "**name**" or "**id**" of any element in the $\text{html}$ as it will cause the code developed by the back-end developer to fail.


```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fruit Chart</title>
    <style>
        
    </style>
</head>
<body>

    <img id="fruit-image" src="" alt="Selected Fruit Image">

    <script>
        const imageURLs = {
            'Apple': 'images/apple.jpg',
            'Banana': 'images/banana.jpg',
            'Cherry': 'images/cherry.jpg'
        };

        function displayFruit() {
            var selectedFruit = document.getElementById('fruit-dropdown').value;
            var imageElement = document.getElementById('fruit-image');

            // The student must complete the switch case logic here.
            switch (selectedFruit) {
                case 'Apple':
                    
                    break;
                case 'Banana':
                    
                    break;
                case 'Cherry':
                    
                    break;
                default:
                    imageElement.src = '';
                    break;
            }
        }
    </script>
</body>
</html>
```
---