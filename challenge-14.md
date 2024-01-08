# Challenge 14 - Edit task details

The user is also able to edit and update the details of a task of a relevent project.

<p align="center">
  <img src="./images/10a.png" width="350px">
</p>

After clicking on the save button, the updated details will be shown on the task detail modal as shown in the image below.

<p align="center">
  <img src="./images/10b.png" width="350px">
</p>

To achieve this, you first have to implement the `updateTask(details, taskId)` method inside the `groupRepository.js` file where a Promise with an UPDATE query is returned. 

The Promise has to resolve a message saying `"success"`.

Afterwards, as done in the previous task you have to,

1. Implement a method called `updateTaskReq(details, taskId)` in the `groupService.js` file which will call the `groupRepository.updateTask(details, taskId)` method and return the response.

2. Create the relevent route that is being called from the frontend in the `groupRoutes.js` file which will call the `groupService.updateTaskReq(details, taskId)` method.

**HINT** - Don't forget to export the defined methods in the necessary files.