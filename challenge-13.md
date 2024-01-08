# Challenge 13 - Edit project details

The user is able to edit and update the details of a project only if that user is the owner of that project.

<p align="center">
  <img src="./images/9a.png" width="350px">
</p>

Note that the above Edit button is only visible if that user is the owner of that project. If the user is not the owner of that project, then the edit button will be hidden.

<p align="center">
  <img src="./images/9b.png" width="350px">
</p>

After clicking on the save button the updated details will be shown on the project detail modal as shown in the image below.

<p align="center">
  <img src="./images/9c.png" width="350px">
</p>

To achieve this, you first have to implement the `updateProject(details, projectId)` method inside the `groupRepository.js` file where a Promise with an UPDATE query is returned. 

The Promise has to resolve a message saying `"success"`.

Next you have to implement a method in the `groupService.js` file in the format shown below.

```javascript
async function updateProjectReq(details, projectId) {
  const response = await groupRepository.updateProject(details, projectId);
  return { response: response, status: httpStatus.OK };
}
```

Finally you have to create the relevent route that is being called from the frontend in the `groupRoutes.js` file as shown below.

```javascript
router.put("<INSERT ROUTE HERE>", async (req, res) => {
    // Retrive and define the necessary parameters from the request body and parameter here


    const response = await groupService.updateProjectReq(details, projectId);
    res.status(response.status).json(response);
});
```

**HINT** - Don't forget to export the defined methods in the necessary files.