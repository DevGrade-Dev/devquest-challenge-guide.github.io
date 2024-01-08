# Challenge 1

#### Please refer to the sub module Hobby Scout for Challenge 1 to Challenge 4

You are building a hobby group recommender system for a social platform that connects people with similar hobbies.

# Challenge 1.a

Implement the `getUsers()` method inside the `userRepository` file. This method should return all the users of `users` table including their respective hobbies and skills. There are separate tables for `hobbies` and `skills`. The user data and the respective hobbies and skills of each user should be returned as an array. This method can be used in the `friendRepository` file to fetch users and therefore, it is recommended to create it before implementing the next challenges.
After successful creation, you will receive the below output:
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
            ]
        },
        {
            "id": 2,
            "email": "ney@nj.com",
            "gender": "Male",
            "firstname": "Neymar",
            "lastname": "Jr.",
            "image_url": "https://pbs.twimg.com/media/EK-YsU9XYAU7R-o?format=jpg&name=medium",
            "hobbies": [
                {
                    "name": "Music",
                    "rate": 1
                },
                {
                    "name": "Soccer",
                    "rate": 5
                },
                {
                    "name": "Video Games",
                    "rate": 2
                }
            ],
            "skills": [
                {
                    "name": "Javascript",
                    "rate": 5
                },
                {
                    "name": "Photography",
                    "rate": 4
                }
            ]
        },
        {
            "id": 3,
            "email": "laflame@cactusjack.com",
            "gender": "Female",
            "firstname": "Travis",
            "lastname": "Scott",
            "image_url": "https://upload.wikimedia.org/wikipedia/commons/thumb/1/14/Travis_Scott_-_Openair_Frauenfeld_2019_08.jpg/500px-Travis_Scott_-_Openair_Frauenfeld_2019_08.jpg",
            "hobbies": [
                {
                    "name": "Music",
                    "rate": 5
                }
            ],
            "skills": [
                {
                    "name": "Java",
                    "rate": 2
                }
            ]
        },
        {
            "id": 4,
            "email": "test@test.com",
            "gender": "Male",
            "firstname": "Mister",
            "lastname": "X",
            "image_url": "https://th.bing.com/th/id/R.9361b3213e181ebaa3f6282d02fab077?rik=VNRw0lKt92xneA&pid=ImgRaw&r=0",
            "hobbies": [
                {
                    "name": "Gym",
                    "rate": 5
                },
                {
                    "name": "Rap",
                    "rate": 2
                },
                {
                    "name": "Sports",
                    "rate": 3
                },
                {
                    "name": "Video Games",
                    "rate": 5
                }
            ],
            "skills": [
                {
                    "name": "Ruby",
                    "rate": 4
                },
                {
                    "name": "Singing",
                    "rate": 5
                }
            ]
        },
        {
            "id": 5,
            "email": "random@user.com",
            "gender": "Female",
            "firstname": "Thomas",
            "lastname": "A. Anderson",
            "image_url": "https://th.bing.com/th/id/OIP.bEl-isZYhCmzsIGyhdEatgHaEK?pid=ImgDet&rs=1",
            "hobbies": [
                {
                    "name": "Gym",
                    "rate": 5
                },
                {
                    "name": "Rap",
                    "rate": 5
                },
                {
                    "name": "Video Games",
                    "rate": 1
                }
            ],
            "skills": [
                {
                    "name": "Dancing",
                    "rate": 3
                },
                {
                    "name": "Docker",
                    "rate": 5
                }
            ]
        },
        {
            "id": 6,
            "email": "liyana@hacktitude.io",
            "gender": "Female",
            "firstname": "Liyana",
            "lastname": "Tan",
            "image_url": "https://i.pinimg.com/originals/29/a8/20/29a82067b71bd9e3df95e1c0ba5c4daf.jpg",
            "hobbies": [
                {
                    "name": "Coding",
                    "rate": 5
                },
                {
                    "name": "Music",
                    "rate": 3
                },
                {
                    "name": "Soccer",
                    "rate": 4
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
            ]
        }
    ]
```

# Challenge 1.b

Complete the `getUser(id)` method inside the userRepository file. It takes `id` which is the user id as an argument and returns the respective user as the output. Here's what you need to do:
1. Return a response message `User not found!` if the user `id` was not found.
