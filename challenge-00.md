# Challenge 0

## Challenge 0.a

In the current application, you may have noticed that at incorrect `login` attempts, the system exposes too much information. For example, the current system displays the below message on the following scenario when the user email is not found.

#### Scenario 1

If the user email does not exist, the system shows the message `User Not Found`

<p align="center">
  <img src="./images/0a.png" width="350px">
</p>

This is a bad security practice, as hackers will be able to verify if an user account is existing by simply testing around the system. Your task is to fix this by ensuring in the above scenario, the system shows the exact same message `User authentication failed`.

## Challenge 0.b

It also displays the below message on the following scenario when the password is not matched with the entered email.

#### Scenario 2

If user email does exists but the password is incorrect, system shows the message `Password Mismatch`

<p align="center">
  <img src="./images/0b.png" width="350px">
</p>

This is a bad security practice, as hackers will be able to verify if an user account is existing by simply testing around the system. Your task is to fix this by ensuring in the above scenario, the system shows the exact same message `User authentication failed`.

Once these are completed, first two tests in `challenge0.test` should succeed. You can verify that by running the the command `npm test`.

## Challenge 0.c

Currently, the system displays a welcome message after successful authentication. The welcome message should include the user's firstname and the right top nav bar should include the users first and last names.

#### Scenario 3

Welcome message displays `Welcome undefined` and top nav bar shows `undefined undefined`

<p align="center">
  <img src="./images/0c.png" width="350px">
</p>

Your task is to retrieve the users firstname and lastname from the backend after successful authentication. Then the firstname will appear in the welcome message and both firstname and lastname will appear in the right hand side of the top nav bar.

Once this is completed, the last test in `challenge0.test` should succeed. You can verify that by running the the command `npm test`.
