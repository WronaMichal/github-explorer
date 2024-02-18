# github-explorer

## Table of contents
- [General info](#general-info)
- [Technologies](#technologies)
- [About the project](#about-the-project)
  
- [Functional and non-functional requirements](#functional-and-non-functional-requirements)
- [Project status](#project-status)
- [Resources](#resources)
- [Contact](#contact)

## General info

This project provide api to list repositories from github for specific user by his login. It also provide data transfer object for exceptions like 'not found repository by username' or 'incorrect accept header' in correct format defined in functional requirements.

## Technologies
* Java 21
* Spring Boot (Web, Webflux)
* Gson
* Lombok
* Swagger

## About the project
### Endpoints:

#### Get user github repositories `http://localhost:7000/v1/api/repository/get?username={username}`

![image](https://github.com/WronaMichal/Assets/blob/main/Postman.png)

## Functional and non-functional requirements

The non-functional requirements that have been set for the application include:
- none

The functional requirements that have been set for the application include:
- Provide feature: list all github repositories for header “Accept: application/json” in format: (Repository Name, Owner Login, For each branch it’s name and last commit sha)
example: \
 ```
{
"repositoryName": "Tennis-App",
        "ownerLogin": "WronaMichal",
        "branches": [
            {
                "name": "2-mvc-skeleton-implementation",
                "sha": "78c2c87ce812780825dfdc4495824958ca4bfee4"
            },
            {
                "name": "main",
                "sha": "f7a772b1027f6480ffbac4e3c675a423d04b5175"
            }
        ]
    },
    {
        "repositoryName": "github-explorer",
        "ownerLogin": "WronaMichal",
        "branches": [
            {
                "name": "master",
                "sha": "be431ba8903f73e76365749990259e325cc90067"
       
            }
        ]
    }
```
- use https://developer.github.com/v3 to provide user repositories
- if given github username dont exist return 404 response in such a format:{ “status”: ${responseCode} “Message”: ${whyHasItHappened} }
example ,
```
{
    "statusCode": 404,
    "message": "GitHub username not found !"
}
```
- if request contain header “Accept: application/xml”, return 406 response in such a format:{ “status”: ${responseCode} “Message”: ${whyHasItHappened} }
example ,
```
{
    "statusCode": 406,
    "message": "No acceptable representation"
}
```


## Project status

The project has been completed, all functional and non-functional requirements have been implemented.

## Setup

1. Open this URL https://github.com/WronaMichal/github-explorer
2. Now we must find the green rectangle where it writes „<>CODE”
3. We select HTTPS and there is a link below that you need to copy
4. The next step is to open IntelliJ And choose File > New > Project from Version Control
5. Then we need to paste our URL from Github, select the path to our project on our PC, and click Clone.
6. Enjoy our Project! 😄

## Resources

📦 Postamn Collection to test API V1:  [github-explorer.postman_collection.zip](https://github.com/WronaMichal/Assets/blob/4097553ca490a15379821ce9fe9b0f0e8a42e12b/github-explorer.postman_collection.zip) \
🧪 Swagger: http://localhost:7000/swagger-ui/index.html 

## Contact

Author: Michał Wrona \
Email: wrona.michal53@gmail.com \
Project Link: https://github.com/WronaMichal/github-explorer
