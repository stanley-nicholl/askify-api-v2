# Askify 2.0 API 
a gSchool Question Queue API
written in Go by [katreinhart](kat.reinhart@gmail.com)

## Askify is a question queue built for students at Galvanize.  
This API is my independent study project for WDI Q4 and is implemented in Go using the Gorilla toolkit for parsing URL tokens and the Negroni framework for handling middleware. 

### Getting started
1. You will need [Go](http://golang.org) installed to run this project. 
1. Fork and clone the repository to your local machine into your ```$GOPATH``` (usually /Users/(your user name)/go/).
1. Navigate into the project folder and run ```go install``` to install dependencies. 
1. You will need a local postgres server running - [here](https://launchschool.com/blog/how-to-install-postgresql-on-a-mac) is a good overview on how to do that.
1. Create a local postgres database called askify_v2_dev. 
1. Change the name of ```.env.sample``` to ```.env``` and edit the file with your credentials or secret key as necessary
1. ```go run main.go``` will run the server locally, and you can test API endpoints from Postman or similar. 
1. ```go build``` will compile the project into an executable binary. 

### API Routes Implemented 
(all API routes begin with ```/api```)
* ```/questions/``` GET, POST
* ```/questions/{id}``` GET, PUT
* ```/questions/{id}/answers``` GET, POST
* ```/questions/{id}/answers/{aid}``` GET
* ```/questions/open``` GET <-- returns all unanswered questions

### Authentication & Authorization
* Authentication routes begin with ```/auth```
* Routes are ```/register``` and ```/login```
* Both auth routes require an "email" and "password" field.
* Auth routes return a JWT token.
* API routes begin with /api/ and are JWT-token protected.
* Use the JWT token returned from register or login as an authorization bearer token to access these routes. 

### Work In Progress
This is a work in progress as of January 2018. 

#### Backlog
* ~~Use ```https://github.com/auth0/go-jwt-middleware``` go-jwt-middleware to protect routes.~~
* Implement Delete functionality? 
* Implement ```/users/{id}/questions``` GET route to see all users' questions

