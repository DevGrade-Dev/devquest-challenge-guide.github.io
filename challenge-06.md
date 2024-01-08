# Challenge 6 - Assign user to the UserGroup and Retrieving groups joined by current user

In this challenge you have to complete another set of two features found at the Join Groups & Joined Group page of Colab Hub

<p align="center">
  <img src="./images/14a.png" width="700px">
</p>

<p align="center">
  <img src="./images/14b.png" width="700px">
</p>

Your task involves completing the codes in these following files:
`groupRepository.js`,`groupService.js`.

1. Implement a method called `addUserToGroup(data)` in the `groupService.js` file which will call a function of same name and parameter from `groupRepository.js` method and return a status code of `200` as a success response when a record is created at the UserGroups table successfully.  
Expected object for `data` parameter:
```json
{
    group_id:"<SELECTED GROUP ID>",
    user_id:"<CURRENT USER ID>"
}
```

2. Implement a method called `getGroupsFromUser(userId)` in the `groupService.js` file which will call a function of same name and parameter from `groupRepository.js` method. It will return an array of groups which matches the provided user id. You will need to make use the mapping from the UserGroups table.


**HINT** 
-  After adding a new mapping at UserGroups table, you can use getGroupsFromUser function to validate if you can retrieve the expected groups joined by the current user.
-  Don't forget to export the defined methods in the necessary files.

