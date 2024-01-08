# Challenge 8 - Shared Documents Upload & Download

After completing Challenge 13 & 14, your users will be able to join groups now. Once you are a part of group, you can go to the Shared Documents page and view the shared documents of your joined group and download them.

<p align="center">
  <img src="./images/16a.png" width="700px">
</p>

<p align="center">
  <img src="./images/16b.png" width="700px">
</p>

Your task involves completing the codes in these following files:
`colabSharedDocsRepository.js`,`colabService.js`.

1. Implement a method called `addNewDoc(data)` in the `colabService.js` file which will call a function of same name and parameter from `colabSharedDocsRepository.js` method and return a status code of `200` as a success response when a record is created at the `colab_shared_docs` table successfully. This function does not actually store the file but it generates a metadata which you can use to grab the file from the actual server where you will be uploading the file to.
Expected object for `data` parameter:
```json
{
    file_name:"<FILE NAME>",
    file_desc:"<FILE DESCRIPTION>",
    file_path:"<FILE PATH>",
    group_id:"<SELECTED GROUP ID>",
    user_id:"<CURRENT USER ID>"
}
```

2. Implement a method called `getDocById(group_id)` in the `colabService.js` file which will call a function of same name and parameter from `colabSharedDocsRepository.js` method. It will return an array of shared document `data` where the `group Id` matches the selected group. 


**HINT** 
-  For the frontend implementation, you can submit the shared document using a `FormData` interface. The file should be stored under the key, `doc`. 
- `File Name` and `File Path` do not need to be passed from the frontend as these information can be derived from the actual file data and the assigned server path to store the files.
-  Don't forget to export the defined methods in the necessary files.

