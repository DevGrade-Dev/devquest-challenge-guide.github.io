# Challenge 3 - Friend Request Management

In this challenge, you are required to implement functionalities related to managing friend requests in the `HobbyScout` application.

## Core Functionalities

1. Send a friend request.
2. Check pending requests (already sent or received).
3. Accept friend requests.
4. Reject firend requests

# Test Cases

The provided test suite covers various scenarios to ensure the proper functionality of friend request management in HobbieSkout.

## Challenge 3.a
 The test ensures that users can successfully send friend requests. It checks if the response contains the word `success` after sending a request. Modify the method `sendReq(data)` inside the `friendRepository` to send a friend request successfully. Here's what you need to do:
 1. Rewrite the SQL query to insert data ('sender_data','recipient_id` and `status` as `"PENDING"`) to the `friends` table in the database.
 2. Return `"success"` after successful insertion.

## Challenge 3.b

 This test verifies that the system detects when a user tries to send a friend request to another user to whom a request has already been sent. Update the correct method in `friendRoutes` inside the `routes` directory.

 API: ```/api/friends/request``` should return ```"Request already sent!"```  for this scenario. Here's what you need to do,
 1. Return `"Request already sent!"` if there exists any record with the same sender_id in the `friends` table.

## Challenge 3.c
This test ensures that the system detects when a user tries to send a friend request to a user who has already sent a request to them. Update the correct method in `friendRoutes` inside the `routes` directory.

API : ```/api/friends/request``` should return ```"Request already received!"``` for this scenario .
1. Return `"Request already received!"` if there exists a friend request from the recipient in the `friends` table.

## Challenge 3.d

This test checks whether the system correctly counts the number of friend requests sent by a user. Your task is to update the method `viewSentReqs(id)` inside the `friendsRepository` to return users to whom requests were sent. Here `id` refers to the `sender_id` attribute of the `friends` table. Query through the `friends` table and check whether there are any records with the given `sender_id`. However, only the `PENDING` requests should return as the number of friend requests sent by a user.

Hint: You can use the `getUser(id)` method in `userRepository` to fetch each user's details and return an array of users whose requests were sent as the output.

If the user doesn't have any sent friend requests, then the method should return an empty array.

If the user has sent any friend requests, then the output should be like this,
```json
 [
        {
            "id": 6,
            "email": "liyana@hacktitude.io",
            "gender": "Female",
            "firstname": "Liyana",
            "lastname": "Tan",
            "image_url": "https://i.pinimg.com/originals/29/a8/20/29a82067b71bd9e3df95e1c0ba5c4daf.jpg",
            "hobbies": [
                {
                    "name": "Soccer",
                    "rate": 4
                },
                {
                    "name": "Coding",
                    "rate": 5
                },
                {
                    "name": "Music",
                    "rate": 3
                }
            ],
            "skills": [
                {
                    "name": "Java",
                    "rate": 3
                },
                {
                    "name": "Javascript",
                    "rate": 4
                },
                {
                    "name": "Photography",
                    "rate": 3
                }
            ],
            "reqId": 4
        }
    ]
```
In the above response, `id` refers to each user's `id` in the `users` table.
For this test case, the method should return an empty array as there are no records with `sender_id` of user `Liyana` where the `status` is `PENDING` in the `friends` table.

## Challenge 3.e

The test retrieves an array of pending friend requests for the authenticated user and validates the response against the expected format. Your task is to implement the `viewPendingReqs(id)` method inside `friendsRepository` to return the users for whom the requests were received. Parameter `id` is the `recipient_id` in the `friends` table.

Hint: You can use the `getUser(id)` method in `userRepository` to fetch each user's details and return an array of users whose requests were received as the output.

If the user hasn't received any friend requests, output should be an empty array and if the the user has received any friend requests then the output should be like this,
```json
[
    {
        "id": 1,
        "email": "siu@cr7.com",
        "gender": "Male",
        "firstname": "Cristiano",
        "lastname": "Ronaldo",
        "image_url": "https://www.irishtimes.com/resizer/geEGpNJqT_hxa139T5HWfq8YdYw=/1600x0/filters:format(jpg):quality(70)/cloudfront-eu-central-1.images.arcpublishing.com/irishtimes/C752OG447LSTHDRHTADVXYWCPQ.jpg",
        "hobbies": [
            {
                "name": "Gym",
                "rate": 4
            },
            {
                "name": "Soccer",
                "rate": 5
            },
            {
                "name": "Sports",
                "rate": 3
            }
        ],
        "skills": [
            {
                "name": "C++",
                "rate": 4
            },
            {
                "name": "Java",
                "rate": 5
            },
            {
                "name": "Python",
                "rate": 3
            }
        ],
        "reqId": 4
    },
]
```
In this response, `reqId` is the `id` attribute of the `friends` table.
After successful implementation, you will be able to view the pending friend requests through the application as below.
<p align="center">
  <img src="./images/3e.png" width="350px">
</p>

Note: The user avatar image can be different; ignore it as it was generated randomly.

## Challenge 3.f

The test ensures that the system can accept a friend request and mark it as accepted.

On successful friend request accept, API: ```/api/friends/${reqId}/accept-request ``` should return ```success``` and in database request, `status` should be updated to ```"ACCEPTED"```. Here's what you have to do,
1. Rewrite the SQL query in the method `acceptReq(id)` inside the `friendsRepository` to accept a friend request by updating the `status` attribute in the `friends` table to `"ACCEPTED"`. Parameter `id` is the `id` attribute in the `friends` table.
2. Return `"success"` after successful implementation.

## Challenge 3.g

The test verifies that the system can reject a friend request and remove it from the pending request list.

On successful rejection , API ```/api/friends/${reqId2}/reject-request``` should return  ```"Request deleted successfully"```. Also, the relevant record should be deleted from the database. Update the method `rejectReq(id)` inside the `friendsRepository` to reject the friend request by deleting the relevant record from the `friend` table. Here's what you have to do,
1. Rewrite the SQL query in the method `rejectReq(id)` inside the `friendsRepository` to delete a friend request by removing the relevant record from the `friends` table. Parameter `id` is the `id` attribute in the `friends` table.
2. Return `"Request deleted successfully"` after successful deletion.
