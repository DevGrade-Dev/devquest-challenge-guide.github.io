# Challenge 9 - Get the relevent groups of user

#### Please refer to the sub module Project Mate for Challenge 9 to Challenge 16 

In this challenge you're supposed to retrieve the groups of the Hobby Hive user and display them on the side bar under the groups list. Currently the groups list will be empty as shown in the image below.

<p align="center">
  <img src="./images/5a.png" width="350px">
</p>

To achieve this, you first have to implement the `getGroupsOfUser(userId)` method inside the `groupRepository.js` file which returns a Promise as shown below.
```javascript
return new Promise((resolve, reject) => {
  knex_db
    .raw(
      `
      <INSERT SQL QUERY HERE>
      `,
      [userid]
    )
    .then((result) => {
      const groups = result;
      resolve(groups);
    })
    .catch((error) => {
      reject(error);
    });
});
```

Your task is to paste the above code block inside the `getGroupsOfUser(userId)` method and add the relevent sql query which uses the `userId` as a parameter to get the specific groups of the user with the passed userId.

**Note** - There are 3 tables as users, groups, and userGroups and you're supposed to get all information regarding the groups of which the current user is a part of.

After successfully retrieving the groups list using the SQL query the relevent groups will be visible as shown in the image below.

<p align="center">
  <img src="./images/5b.png" width="350px">
</p>
