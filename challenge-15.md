# Challenge 15 - Update project status

In this challenge you have to enable the user to update the status of a project and the project has to be switched to the correct swim lane in the project dashboard depending on its status.

<p align="center">
  <img src="./images/11a.png" width="350px">
</p>

<p align="center">
  <img src="./images/11b.png" width="350px">
</p>

To achieve this, you have to impelement the `updateProjectStatus(projectId, status)` method in the `groupRepository` file and this time it has to be returning a Promise which has an UPDATE query which updates the status of the project using the projectId. 

The Promise has to resolve a message saying `"success"`.

Afterwards, as done in the previous tasks you have to,

1. Implement a method called `updateProjectStatusReq(projectId, status)` in the `groupService.js` file which will call the `groupRepository.updateProjectStatus(projectId, status)` method and return the response.

2. Create the relevent route that is being called from the frontend in the `groupRoutes.js` file which will call the `groupService.updateProjectStatusReq(projectId, status)` method.

**HINT** - Don't forget to export the defined methods in the necessary files.