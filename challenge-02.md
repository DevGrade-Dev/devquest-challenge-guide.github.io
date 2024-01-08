# Challenge 2

Welcome to HobbyScout, a platform designed to help you find friends who share similar hobbies and interests. Your mission is to implement core functionalities for the HobbyScout application.

## Challenge 2.a

In this challenge, you are required to implement the HobbyScout algorithm in the `getSuggestedFriends(userId)` method inside the `friendRepository` file. This method takes a `userId` as an argument and returns a list of suggested friends (excluding friends) for the given user based on their hobbies. The API endpoint for this functionality is `/api/friends/{userId}/suggestions`.

The `getSuggestedFriends(userId)` method should fetch data from the database and find friends who share similar hobbies with the given user. The response should include information about each suggested friend, including their `id`, `email`, `firstname`, `lastname`, `image_url`, `hobbies`, and `skills`.
Each hobby is rated from 1 to 5 based on their interests.

For ex: User `Liyana` has below hobbies,
```json
"hobbies": [
      { "name": "Coding", "rate": 5 },
      { "name": "Music", "rate": 3 },
      { "name": "Soccer", "rate": 4 },
]
```

User `Cristiano` has following hobbies,
```json
"hobbies": [
          { "name": "Gym", "rate": 4},
          {"name": "Soccer","rate": 5},
          {"name": "Sports","rate": 3},
]
```

As you can see, both have a similar hobby `Soccer`. But their rates are different. Here's what you need to do,
1. Check users with similar hobbies.
2. Find the rate difference (absolute difference) of the similar hobbies of the respective users (in the above example, it should be 1).
3. Get the users (as an array) who have the minimum rate difference.
    - You need to find the rate difference of the users.
    - Sort them according the the rate differences found. 
    - Find the minimum rate difference of the users.
4. Check whether any of those users are already friends by queuing with the `friends` table.
5. If so, remove them from the list of users above.
6. Return the first 5 users (who have the lowest rate difference) as the output.

Note: Users who are already friends shouldn't show up as suggested friends.

After successful creation, the method should return the following suggested users as the output for user `Liyana`.

```json
[
      {
        "id": 1,
        "email": "siu@cr7.com",
        "firstname": "Cristiano",
        "gender": "Male",
        "lastname": "Ronaldo",
        "image_url":
          "https://www.irishtimes.com/resizer/geEGpNJqT_hxa139T5HWfq8YdYw=/1600x0/filters:format(jpg):quality(70)/cloudfront-eu-central-1.images.arcpublishing.com/irishtimes/C752OG447LSTHDRHTADVXYWCPQ.jpg",
        "hobbies": [
          {
            "name": "Gym",
            "rate": 4,
          },
          {
            "name": "Soccer",
            "rate": 5,
          },
          {
            "name": "Sports",
            "rate": 3,
          },
        ],
        "skills": [
          {
            "name": "C++",
            "rate": 4,
          },
          {
            "name": "Java",
            "rate": 5,
          },
          {
            "name": "Python",
            "rate": 3,
          },
        ],
      },
      {
        "id": 2,
        "email": "ney@nj.com",
        "firstname": "Neymar",
        "gender": "Male",
        "lastname": "Jr.",
        "image_url":
          "https://pbs.twimg.com/media/EK-YsU9XYAU7R-o?format=jpg&name=medium",
        "hobbies": [
          {
            "name": "Music",
            "rate": 1,
          },
          {
            "name": "Soccer",
            "rate": 5,
          },
          {
            "name": "Video Games",
            "rate": 2,
          },
        ],
        "skills": [
          {
            "name": "Javascript",
            "rate": 5,
          },
          {
            "name": "Photography",
            "rate": 4,
          },
        ],
      },
    ];
```
In the above response, `id` refers to each user's `id` in the `users` table.
After successful implementation, you will be able to view the suggested friends through the application, as below for user `Liyana`.
<p align="center">
  <img src="./images/2a.png" width="350px">
</p>
Note: The user avatar images can be different; ignore them as they were generated randomly.
