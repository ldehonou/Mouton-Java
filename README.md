# Secure Coding project #

The goal of the project is to build a Node js backend by taking in consideration the security of the application.

## Stack ##
* NodeJs and Typescript
* Postgresql database
* TypeORM
* Chai and Mock for testing

## Questions TP1 ##

Question 1 :
> 1- Clean the database before each test case allows to create special data required for each test and obtain the expected behavior.
> 2- If the database is filled with a lot of data, the queries may take longer than expected. So we should keep only the required data.
> 3- Using data intended only for testing ensures the integrity of the tests

Question 2:
>The error thrown in test case "should raise error if email is missing" is an SQL error.

Question 3:
>Models validations allow to check the type and the quality of the data used. So we can prevent some vulnerabilities that are based on "poor quality" data.
>For example, if we want an application with sensitive data that we want to protect with encrypted passwords. With the constrain, we can verify if the password is well encrypted when they are >stored in the database. 
>With the typescript validation, we can verify if the password entered meets the selected conditions. 
>So it's more secure to have two validations, one for the type and an other one before the saving of the data.

Question 4:
>The database mechanism wich can be leveraged for security hardening in case a validation fails is the database trigger.

## Questions TP2 ##

Question 1:
>REST "methods" are composed of :
>- the  HTTP verb, a specific action that can "slightly" change in function of the path.
>- the path, leading to the ressources.
>Here are some good practices about the REST naming conventions :
>1) Avoid using file extensions because it adds complexity.
>2) Indicate the version of the API because it's easier to indicate the change made between two version.
>3) Use plural names for the resources instead of ids or singular names (unless for unique resources).
>4) Use hyphens and avoid to have a long name difficult to read.

Question 2:
>POST /web-api/users : create a new user based on information received
>POST /web-api/sessions : create a new session after validation of the user's information

Question 4: how behaves fastify:
- if no json schema is provided for any of body, query and params ?
>The request will be exectued without any validation.
- if the client submits an unknown property, according to the JSON schema?
>Fastify will ignore the unknown property.
- if the client omits a required property, according to the JSON schema?
>The error 400 with a message indicating the missing property will be returned.

Question 5:


| Criteria                                             | Stateful session                                                                                                            | JWT                                                                                                         |
|------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------|
| Scalability                                          |Increase the user number = issues with performance so we need at the start a good architecture to ensure a good functionment |The tokens used are stored on the client side, so there is no session state stored on the backend            |
| Architecture Complexity                              |Required a backend service for the session management                                                                        |Simpler : only required client to store and send token                                                       |
| Type and quantity of information known by the client |Information stored by the backend : state of the session so on client side : id to identify the session on the backend       |Backend generate a token with information cryptographically signed and sent to the client to be stored       |
| Revocation strategy                                  |Easier : we just have to invalidate an id or add a duration of inactivity                                                    |More difficult : we can add a list of revoked tokens but it can have a cost on the performance               |
| Impact if a session leaks                            |Important because with a session leak, we can find the identity of a user and the information related to the session.        |Limited because a token has only limited in time data and this data aren't sensible                          |
| Common weaknesses due to misconfiguration            |Due to a bad configuration on the backend or the session management                                                          |Due to programming errors, bad configuration on the client side or the bad implementation of JWT tools       |
| Client-side strategy to protect and submit the token |To be sure that the session identfier is stored in a secured way we can use a cookie HttpOnly or a local secured storage     |To be sure that the token is stored in a secured way we can use a cookie HttpOnly or a local secured storage |
| Additional libraries requirerement                   |We can use additional libraries to manage sessions for example. But it increase the complexity of the architecture           |We cane use addition libraries to generate or validate tokens on the backend. It's usually easier            |

Question 6:
