# Challenge 11 - Add new project to a group

The user can click on either one of those groups displayed and get the relevent project and task details regarding the group as displayed in the image below.

<p align="center">
  <img src="./images/7a.png" width="350px">
</p>

In this challenge your task is to implement the funtionaility to add a new project to the relevent group.

When the user clicks on the `Add Project +` button on the right hand top corner of the page, a modal will be visible and when the user enters project details and clicks on the `Save` button an alert will be displayed with a relevent message.

<p align="center">
  <img src="./images/7b.png" width="350px">
</p>

After the page reloads and upon clicking on the relevent group, the newly added project will be displayed on the `To-Do` column.

<p align="center">
  <img src="./images/7c.png" width="350px">
</p>

To achieve this, you first have to implement the `addNewProject(projectDetails)` method inside the `groupRepository.js` file similar to the previous task but in this case the SQL query will be an INSERT query with all the details obtained in the `projectDetails` argument but in the order of the columns in the projects table.

The Promise has to resolve a message saying `"success"` after successfully saving the project details in the projects table in the database.

**Note** - Always cross check with the database tables whether the API calls work properly and the database has been updated. You can always run `knex run:seed` to get back to the default data in the database.