# SAuth API - Assignment for the position of Software Developer - Backend - Java

This is an assignment for the interview of Backend Tech Lead in Java Stack. 

To complete this assignment, you're expected to complete the following tasks:

1. Deploy a test project on your local environment
2. Write APIs as per the specifications given below
3. Upload it on a public Github repository
4. Share the repository URL with us
5. Keep the project ready to run at the time of tech interview
6. Create [Postman](https://www.postman.com/) package to test and demo your APIs

You don't need to do the following but it will be a plus: 
1. Deploy the database and application on a live hosted server

Selection for the interview will happen based on your coding practices. You will be required to run and demo the project at the time of interview.


# Usecase

SAuth REST APIs will be used by various applications to store and fetch their user information. 

Applications using your APIs will be indentified using an authentication token. 

# API Specs

## **POST /register**

Register a new auth token

## Headers

None

## Path Parameters

None

## Request Body Parameters (JSON)

None

## Response

Newly generated unique authentication token

```
{      
    success: true,   
    authToken: "slkjf45987495f54o7ghoni8josy4h"     
}
```
  
---
## POST /user

Create a new user record

## Headers

| Name | Description | Value | Example Value |
|---|---|---|---|
| Authorization | Authorization token to identify which application is using your APIs | Bearer {YourAuthToken} | Bearer slkjf45987495f54o7ghoni8josy4h |

## Path Parameters

None

## Request Body Parameters (JSON)

| Parameter name | Required | Accepts | Description | 
|----|----|----|----|
| name | true | String | Users name | 
| email | false | String | Users email address | 
| mobilenumber | false | Array of Strings | Multiple mobile numbers entered by user |
| city | true | String | Users city |

**Sample JSON Body**
```
{
    name: "John Doe",`  
    email: "john@example.com",
    mobilenumber: [
        "9191919191",
        "9155667678"
    ]  
}
```
## Response

ID of the newly registered user.

```
{
    success: true,  
    userId: 5  
}
```


---
## GET /user

Fetch list of all users registered by an application

## Headers

| Name | Description | Value | Example Value |
|---|---|---|---|
| Authorization | Authorization token to identify which application is using your APIs | Bearer {YourAuthToken} | Bearer slkjf45987495f54o7ghoni8josy4h |

## Path Parameters
None

## Request Body Parameters (JSON)
None


## Response

List of users registered for the auth token provided. 

```
{
    success: true,  
    users: [
        {  
            name:"John Doe",  
            email:"john@example.com",   
            mobilenumber:[
                "9191919191",
                "9155667678"
            ]   
        },  
        {  
            name:"Merry Jane",     
            mobilenumber:[
                "9797979797",
                "9898989898"
            ]   
        }  
    ]  
}

