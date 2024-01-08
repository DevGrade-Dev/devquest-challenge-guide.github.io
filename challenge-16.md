# Challenge 16 - Update task status

In this challenge you have to enable the user to update the status of a task as similar to the previous challenge.

<p align="center">
  <img src="./images/12a.png" width="350px">
</p>

<p align="center">
  <img src="./images/12b.png" width="350px">
</p>

To achieve this, you have to impelement the `updateTaskStatus(taskId, status)` method in the `groupRepository` file and this time it has to be returning a Promise which has an UPDATE query which updates the status of the task using the taskId. 

The Promise has to resolve a message saying `"success"`.

Afterwards as done in the previous task you have to,

1. Implement a method called `updateTaskStatusReq(taskId, status)` in the `groupService.js` file which will call the `groupRepository.updateTaskStatus(details, taskId)` method and return the response.

2. Create the relevent route that is being called from the frontend in the `groupRoutes.js` file which will call the `groupService.updateTaskStatusReq(taskId, status)` method.

**HINT** - Don't forget to export the defined methods in the necessary files.