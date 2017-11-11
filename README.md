Testing Graphcool facebook resolver functions
==============

Graphcool initialization
--------------
in command line: <br>

* graphcool init 

* graphcool add-template graphcool/templates/auth/facebook

*uncomment facebookAuthentication and loggedInUser functions in graphcool.yml*

* graphcool deploy

Register a Facebook App with Authentication
--------------
* make sure its a webapp
* create a login product
* add callback redirect
* replace __APP_ID__ with facebook app id in login.html

Retrieve a Facebook Token
--------------
* create server with python
* command line: python -m SimpleHTTPServer
* http://localhost:8000/login.html

* retrieve token from console

Test Login in Graphcool Playground
--------------
```
mutation {
	authenticateUser(facebookToken: "token") {
		id
		token
	}
}
```