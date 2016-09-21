# Rails API Diagnostic

Place your responses inside the fenced code-blocks where indicated by comments.

What is the purpose of a backend?

```bash
A backend is responsible for storing & maintaining data (and relationships
between data), and creating/reading/updating/destroying data in response to
requests from the front end (i.e. clients). It also performs authentication and
validation in order to maintain the integrity and security of data.

A backend also allows for interaction between clients by providing a central
location for the storage of any state that multiple clients may want to
interact with or use to communicate with each other.
```

Which layer in the MVC pattern is used by the controller to fetch data?

```bash
The model layer
```

Which layer in the MVC pattern communicates with the model?

```bash
The controller
```

Why don't we use views in our interpretation of the MVC pattern?

```bash
Because we are building single-page applications that get HTML from the server
only once (at page load), and subsquently render all view states in the client
using JSON data obtained from the server via AJAX.
```

What does C.R.U.D stand for?

```bash
Create, Read, Update, Destroy
```

In which part of the MVC pattern can we find C.R.U.D actions?

```bash
The controller.
```

List at least 5 standard actions that C.R.U.D corresponds to?

```bash
Create, Show, Index, Update, Destroy
```

A user action fires a `GET` request for `/persons/1`. Explain in detail each step
required for data to be returned to the client. (bullet points or ordered list)

```bash
- client sends a 'GET' request to the server with the path '/persons/1'
- on the server side, router hears request and matches it to the action persons#show
- controller fires the persons#show action, which tells the Person model to get
  information about the Person object with an id of 1
- model queries the database table 'persons' for the row with and id of 1
- assuming success, model takes the information returned by the database and
  gives it to the controller
- controller packages the information about Person 1 into a JSON string
  containing the data and a success message, and hands it to the router along
  the same path the request came in on
- router sends the response back out to the client
- client receives the request and does something with it, possibly rendering a
  new view state (if client is a browser) or simply displaying the raw response
  (if client is a cURL request)
```

What is the command to generate a new rails-api app?

```bash
rails-api new <app_name>
```

What is the command to start an instance of a rails server?

```bash
rails s
```

What are the commands to drop, create and migrate a database? (3 bullet points)

```bash
- db:drop
- db:create
- db:migrate
```

What is the command to scaffold a pet with a name and age attributes (hint:
Also think of the data types for each attribute)?

```bash
rails-api g scaffold pet name:string age:integer
```
