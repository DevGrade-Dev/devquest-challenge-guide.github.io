# Challenge 5 - Search For Groups With Keyword and Create New Groups

#### Please refer to the sub module Colab Hub for Challenge 1 to Challenge 4

In this challenge you have to complete the two features found at the Join Groups page of Colab Hub

<p align="center">
  <img src="./images/13a.png" width="700px">
</p>

<p align="center">
  <img src="./images/13b.png" width="700px">
</p>

Your task involves completing the codes in these following files:
`groupRepository.js`,`groupService.js`.

1. Implement a method called `getGroupsFromKeyword(keyword)` in the `groupService.js` file which will call a function of same name and parameter from `groupRepository.js` method and return an array containing the groups matching to the keyword provided from the frontend.

2. Implement a method called `addNewGroup(data)` in the `groupService.js` file which will call a function of same name and parameter from `groupRepository.js` method and return a status code of `200` as a success response when a new group is created successfully.

Expected object for `data` parameter:
```json
{
    group_name:"<GROUP NAME>",
    group_desc:"<GROUP DESCRIPTION>"
}
```


**HINT** 
- When searching for groups using a keyword, you should consider what happens when the keyword returns an empty array. 
- When inserting a new group into the Groups table, it is useful if you return the new `Id` of the created group.
- Don't forget to export the defined methods in the necessary files.

