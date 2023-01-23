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

| Criteria | Stateful Session | JWT |
| Scalability | --- | --- |
| Architecture Complexity | --- | --- |
| Type and quantity of information known by the client | --- | --- |
| Revocation strategy | --- | --- |
| Impact if a session leaks | --- | --- |
| Common weaknesses due to misconfiguration | --- | --- |
| Client-side strategy to protect and submit the token | --- | --- |
| Additional libraries requirerement | --- | --- |

Question 6:
