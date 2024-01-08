# Challenge 12 - Add new task to a project

The user can now click on the newly created project card and view the project details on the pop-up modal as shown below.

<p align="center">
  <img src="./images/8a.png" width="350px">
</p>

In this challenge your task is to implement the funtionaility to add a new task to the relevent project.

When the user clicks on the `Add Task +` button, the modal content will be changed and when the user enters the task details and clicks on the `Save` button, an alert will be displayed with a relevent message.

<p align="center">
  <img src="./images/8b.png" width="350px">
</p>

After the page reloads and upon clicking on the relevent project the newly added task will be displayed under the tasks list of that project.

<p align="center">
  <img src="./images/8c.png" width="350px">
</p>

To achieve this, you first have to implement the `addNewTask(taskDetails)` method inside the `groupRepository.js` file similar to the previous tasks but in this case the SQL query will be an INSERT query with all the details obtained in the `taskDetails` argument but in the order of the columns in the tasks table.

The Promise has to resolve a message saying `"success"` after successfully saving the task details in the tasks table in the database.

**Note** - Always cross check with the database tables whether the API calls work properly and the database has been updated. You can always run `knex run:seed` to get back to the default data in the database.