# Challenge 7 - Whiteboard Save & Load

After completing Challenge 12 & 13, your users will be able to join groups now. Once you are a part of group, you can go to the Whiteboard page and view the whiteboard of your joined group.

<p align="center">
  <img src="./images/15a.png" width="700px">
</p>

<p align="center">
  <img src="./images/15b.png" width="700px">
</p>

Your task involves completing the codes in these following files:
`colabWhiteBoardRepository.js`,`colabService.js`.

1. Implement a method called `addWhiteBoardData(data)` in the `colabService.js` file which will call a function of same name and parameter from `colabWhiteBoardRepository.js` method and return a status code of `200` as a success response when a record is created at the `colab_whiteboard` table successfully. Since, the whiteboard is shared by a group, you may need to `UPDATE` an existing record if there is a row with selected `group ID`.
Expected object for `data` parameter:
```json
{
    whiteboard_json:"<JSON STRING>",
    group_id:"<SELECTED GROUP ID>",
    user_id:"<CURRENT USER ID>"
}
```

2. Implement a method called `getWhiteBoardDataByGroup(group_id)` in the `colabService.js` file which will call a function of same name and parameter from `colabWhiteBoardRepository.js` method. It will return the whiteboard `data`. This will allow the Whiteboard page to restore the whiteboard content if a group member has made some changes. 


**HINT** 
-  Make sure to check your JSON is submitted as a string when you are calling the API.
-  Don't forget to export the defined methods in the necessary files.

