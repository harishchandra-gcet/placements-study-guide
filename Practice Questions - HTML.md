# Practice Questions - HTML

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