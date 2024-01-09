# Challenge 17 - Friend Removal and Request Cancellation

In this challenge, you are required to implement functionalities related to removing friends and canceling sent friend requests in the `HobbyScout` application.

## Core Functionalities

1. Remove a friend.
2. Cancel a sent friend request.

# Test Cases

The provided test suite covers various scenarios to ensure the proper functionality of friend removal and request cancellation in HobbyScout.

## Challenge 17.a

The test ensures that users can successfully remove a friend. It checks if the response contains the phrase `Friend removed successfully!` after removing a friend. Modify the method `removeFriend(id)` inside the `friendRepository` to remove a friend successfully. Here's what you need to do:  
 1. Rewrite the SQL query to delete the friend relationship from the `friends` table based on the provided request id.  
 2. Return `"Friend removed successfully!"` after successfully removing the friend relationship.

## Challenge 17.b

This test verifies that the system detects when a user tries to remove a user who is not in their friend list. Update the correct method in `friendRoutes` inside the `routes` directory.

API: ```/api/friends/${reqId}/remove-friend``` should return ```"Friend not found!"```  for this scenario. Here's what you need to do,  
 1. Return `"Friend not found!"` if there is no friend relationship with the provided request id in the `friends` table.

## Challenge 17.c

This test ensures that users can successfully cancel a friend request that they have sent. It checks if the response contains the phrase `Request cancelled successfully!` after cancelling a friend request. Modify the method `cancelReq(id)` inside the `friendRepository` to cancel a sent friend request successfully. Here's what you need to do:  
 1. Rewrite the SQL query to delete the friend request from the `friends` table based on the provided request id.  
 2. Return `"Request canceled successfully!"` after successfully canceling the friend request.

## Challenge 17.d

This test verifies that the system detects when a user tries to cancel a friend request that is not pending. Update the correct method in `friendRoutes` inside the `routes` directory.

API: ```/api/friends/${reqId}/cancel-request``` should return ```"Request not found!"```  for this scenario. Here's what you need to do,  
 1. Return `"Request not found!"` if there is no pending friend request with the provided request id in the `friends` table.
