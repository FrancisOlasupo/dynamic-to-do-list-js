Create a To-Do List application where users can add, display, and remove tasks.

This task focuses on utilizing advanced DOM manipulation techniques to interact dynamically with the webpage.

Overview
You are tasked with developing a To-Do List application that allows users to add tasks, display them, and remove tasks. This application will utilize advanced DOM manipulation techniques.

Step-by-Step Guide
Setup Event Listener for Page Load:

At the beginning of your script, use document.addEventListener to listen for the 'DOMContentLoaded' event. This ensures your JavaScript code runs after the HTML document has fully loaded. Place all your subsequent code inside the callback function of this event listener.
Select DOM Elements:

Use document.getElementById to select the “Add Task” button and store it in a constant named addButton.
Similarly, select the input field where users enter tasks (id="task-input") and the unordered list (id="task-list") that will display the tasks. Store these references in constants named taskInput and taskList, respectively.
Create the addTask Function:

Define a function named addTask. This function will be responsible for adding new tasks to the list.
Inside addTask, retrieve and trim the value from the task input field. Store this value in a variable named taskText.
Check if taskText is not empty (""). If it is empty, use alert to prompt the user to enter a task.
Task Creation and Removal:

Within the addTask function, if taskText is not empty:
Create a new li element. Set its textContent to taskText.
Create a new button element for removing the task. Set its textContent to "Remove", and give it a class name of 'remove-btn'.
Assign an onclick event to the remove button that, when triggered, removes the li element from taskList.
Append the remove button to the li element, then append the li to taskList.
Clear the task input field by setting taskInput.value to an empty string.
Attach Event Listeners:

Add an event listener to addButton that calls addTask when the button is clicked.
Add an event listener to taskInput for the 'keypress' event to allow tasks to be added by pressing the “Enter” key. Inside this event listener, check if event.key is equal to 'Enter' before calling addTask.
Invoke the addTask function on DOMContentLoaded. - Outside addTask, add an event listener to document for the DOMContentLoaded event. Set the callback function to invoke addTask. This ensures your data fetching logic runs once the HTML document has fully loaded.


Enhance the To-Do List application by enabling it to save tasks in Local Storage, thus allowing the tasks to persist across browser sessions.

Detailed Instructions for JavaScript Implementation
Initialize and Load Tasks:

At the start of your script (inside the 'DOMContentLoaded' listener if continuing from the previous task), check Local Storage for an existing list of tasks.
Use localStorage.getItem('tasks') to retrieve the task list. If tasks are found, parse them from JSON to an array and populate the task list on the page.
Update Task Addition Functionality:

Modify the addTask function to also save tasks to Local Storage whenever a new task is added.
After appending the new task to the DOM, update your tasks array and save it back to Local Storage by serializing the array to JSON using JSON.stringify().
Implement Task Removal with Local Storage Update:

When a task is removed by clicking the “Remove” button, also remove it from the tasks array in your JavaScript.
Then, update Local Storage with the new array to reflect this change.
Code for Loading Tasks from Local Storage:

Write a function that loads tasks from Local Storage when the page loads.
This function should create task elements in the DOM for each task found in Local Storage, ensuring the list reflects saved data.
Saving Tasks to Local Storage:

Every time a task is added or removed, update the array of tasks in your script, then save this updated array to Local Storage.
Ensure the tasks remain available even after the browser is closed or refreshed.