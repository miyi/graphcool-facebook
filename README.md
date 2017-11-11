Testing Graphcool facebook resolver functions
==============

Graphcool initialization
--------------
in commandline:
-graphcool init 
-graphcool add-template graphcool/templates/auth/facebook

*uncomment facebookAuthentication and loggedInUser functions in graphcool.yml*

-graphcool deploy

Register a Facebook App with Authentication
--------------
-make sure its a webapp
-create a login product
-add callback redirect

Retrieve a Facebook Token
--------------
-create a server with python
-command line: python -m SimpleHTTPServer
-http://localhost:8000/login.html
-retrieve token from console

Test Login in Graphcool Playground
--------------
mutation {
	authenticateUser(facebookToken: "token") {
		id
		token
	}
}