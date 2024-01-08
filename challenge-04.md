### Challenge 4.a

The test retrieves the list of accepted friends for the authenticated user from the database. It then sends GET requests to the appropriate endpoints to fetch the details of each friend based on their `id`. The test validates that the responses contain the correct information for each friend, as shown below.

Implement the method `viewFriends(id)` inside the `friendRepository` to return the friends in the `friends` table. Check whether there are records where the respective user has sent a request whose status is `ACCEPTED` and the user received a request whose status is `ACCEPTED`. The parameter `id` in the method `viewFriends(id)` refers to the `id` attribute in the `users` table to fetch the friends for a corresponsing user. Then return the list of friends as below.

Hint: You can use the `getUser(id)` method in `userRepository` to fetch each user's details and return an array of users as friends.

API for the user `Liyana`, `http://127.0.0.1:3000/api/friends/6`

Expected output for user `Liyana`,

```json
[
      {
        "id": 3,
        "email": "laflame@cactusjack.com",
        "gender": "Female",
        "firstname": "Travis",
        "lastname": "Scott",
        "image_url":
          "https://upload.wikimedia.org/wikipedia/commons/thumb/1/14/Travis_Scott_-_Openair_Frauenfeld_2019_08.jpg/500px-Travis_Scott_-_Openair_Frauenfeld_2019_08.jpg",
        "hobbies": [
          {
            "name": "Music",
            "rate": 5,
          },
        ],
        "skills": [
          {
            "name": "Java",
            "rate": 2,
          },
        ],
        "reqId": 2
      },
      {
        "id": 5,
        "email": "random@user.com",
        "gender": "Female",
        "firstname": "Thomas",
        "lastname": "A. Anderson",
        "image_url":
          "https://th.bing.com/th/id/OIP.bEl-isZYhCmzsIGyhdEatgHaEK?pid=ImgDet&rs=1",
        "hobbies": [
          {
            "name": "Video Games",
            "rate": 1,
          },
          {
            "name": "Gym",
            "rate": 5,
          },
          {
            "name": "Rap",
            "rate": 5,
          },
        ],
        "skills": [
          {
            "name": "Dancing",
            "rate": 3,
          },
          {
            "name": "Docker",
            "rate": 5,
          },
        ],
        "reqId": 4
      },
    ]

```
In the above response, `id` refers to each user's `id` in the `users` table.
`reqId` is the `id` attribute of the `friends` table.
After successful implementation, you will be able to view the friends through the application, as shown below.
<p align="center">
  <img src="./images/4a.png" width="350px">
</p>
Note: The user avatar image can be different; ignore it as it was generated randomly.
