# Challenge 18 - Paginated Keyword Search  

In this challenge, you are required to implement paginated search functionalities in the `HobbyScout` application. The search should be based on user information such as First Name, Last Name, skills, and hobbies, allowing users to use a keyword for more refined results.

## Core Functionalities

1. Get paginated search results without a keyword.
2. Get paginated search results with a keyword.

# Test Cases

The provided test suite covers various scenarios to ensure the proper functionality of paginated keyword search in HobbyScout. The API endpoint for this functionality is `/api/friends/{userId}/search`.

## Challenge 18.a

The test ensures that users can get paginated search results without providing a keyword. It checks if the response contains the expected user information after a search. Modify the method `getPeopleFromKeyword(id, keyword, pageNumber)` inside the `friendsRepository` to handle paginated searches without a keyword. Here's what you need to do:  

1. Use SQL queries to retrieve paginated search results without a keyword (empty keyword) based on the provided user `id` (Authenticated user) and the page number.
2. Exclude the authenticated user from the results.
3. Return the response in the specified format, including user information, friend status, and friend request ID.

## Challenge 18.b

This test verifies that users can get paginated search results with a keyword. It checks if the response contains the expected user information after a search. Modify the method `getPeopleFromKeyword(id, keyword, pageNumber)` inside the `friendsRepository` to handle paginated searches with a keyword. Here's what you need to do:

1. Use SQL queries to retrieve paginated search results with a keyword based on the provided user `id` (Authenticated user) and the page number.
2. Exclude the authenticated user from the results.
3. Check the keyword within users' first and last names, as well as their skills and hobby names.
4. Return the response in the specified format, including user information, friend status, and friend request ID.

### Example

Let's consider a scenario where the authenticated user has the ID `1`. We want to perform a paginated search for users matching a keyword. The pagination limit per page is set to 3.

#### Request:

```json
POST /api/friends/1/search
{
  "keyword": "Java",
  "page": 1
}
```

#### Result:

```javascript
[{
    id: 2,
    email: "jhalpert@office.com",
    gender: "Male",
    image_url: "https://upload.wikimedia.org/wikipedia/en/7/7e/Jim-halpert.jpg",
    firstname: "Jim",
    lastname: "Halpert",
    sender_id: 1,
    recipient_id: 2,
    status: "PENDING",
    reqId: 1,
  },
  {
    id: 3,
    email: "pbeesly@office.com",
    gender: "Female",
    image_url: "https://upload.wikimedia.org/wikipedia/en/6/67/Pam_Beesley.jpg",
    firstname: "Pam",
    lastname: "Beesly",
    sender_id: null,
    recipient_id: null,
    status: null,
    reqId: null,
  },
  {
    id: 6,
    email: "rhoward@office.com",
    gender: "Male",
    image_url: "https://upload.wikimedia.org/wikipedia/en/9/91/Ryan_Howard_%28The_Office%29.jpg",
    firstname: "Ryan",
    lastname: "Howard",
    sender_id: null,
    recipient_id: null,
    status: null,
    reqId: null,
  },
]
```

In this example:
- We perform a paginated search for users with the keyword "Java".
- The keyword "Java" is checked in both the user's firstname and lastname, as well as their skills and hobbies.
- If the keyword is present in any of these fields, the user is included in the results.
- Therefore all users that have either "Java" or "Javascript" as one of their skills are included in the results.
- The `sender_id` and `recipient_id` are based on the logged-in user (ID 1). If neither the sender nor recipient is the logged-in user, all fields (`sender_id`, `recipient_id`, `status`, `reqId`) are null.

# Implementation Notes

- This search functionality is paginated, allowing users to navigate through multiple pages of search results. The pagination limit per page is set to **3**.
- Users can use a keyword in the search, which may be present in the user's firstname, lastname, skills, or hobbies.
- The search is case-insensitive, ensuring that users can find results regardless of the letter casing used in the keyword.
- The authenticated user is excluded from the search results.
- The results are in the order of their user ID.
- The POST request should include the following parameters in the request body:
  - `keyword`: The search keyword. `""` for empty keyword search.
  - `page`: The page number for paginated results.
- The response format includes the following user information:
  - `id`: User's unique identifier.
  - `email`: User's email address.
  - `gender`: User's gender.
  - `image_url`: URL of the user's profile image.
  - `firstname`: User's firstname.
  - `lastname`: User's lastname.
  - `sender_id`: ID of the user who sent the friend request.
  - `recipient_id`: ID of the user who received the friend request.
  - `status`: Friend request status (PENDING, ACCEPTED, `null` if not applicable).
  - `reqId`: ID of the friend request (`null` if not applicable).
- Fields (`sender_id`, `recipient_id`, `status`, `reqId`) may be null depending on the user's relationship status or the absence of a friend request.