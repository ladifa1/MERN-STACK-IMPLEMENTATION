# MERN STACK IMPLEMENTATION

## BACKEND CONFIGURATION

Update ubuntu 


`sudo apt update`
![](images/1.png)

Upgrade ubuntu

`sudo apt upgrade`
![](images/2.png)

Get Node.js location from ubuntu repositories

`curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -`

![](images/3.png)

Install Node.js 

`sudo apt-get install -y nodejs`
![](images/installnode.png)

Verify node installation 

`node -v`

`npm -v`

![](images/4.png)




--------------

**TO-DO APPLICATION SETUP**

Create new directory and initalize project 

`mkdir Todo`

`npm init`


![](images/5.png)

Configure package.json file

![](images/6.png)

Run ls to confirm package.json 
![](images/7.png)

---------
Install Expressjs 

`npm install express`
![](images/8.png)

Create a file index.js and check with ls

`touch index.js`

`ls`

![](images/10.png)

Install dotenv

`npm install dotenv`
![](images/11.png)

Open index.js

`vim index.js`
![](images/12.png)

Add the code below into the file
![](images/index.png)

Start server 

`node index.js`
![](images/runnode.png)

Add inbound rule to allow access via tcp port 5000 in EC2 security groups

![](images/13.png)

Access server via browser

![](images/expressjs.png)

**Create routes that will manage To-do application**



`mkdir routes` 

Create file api.js 

`touch api.js`

open api.js

`vim api.js`


![](images/14.png)

Add the code below in api.js
![](images/15.png)



------------------

**Create models**

Install mongooose

`npm install mongoose`

![](images/16.png)

In Todo directory create folder models

`mkdir models`

Create file todo.js

`touch todo.js`

open todo.js

`vim todo.js`


![](images/17.png)

Add the code below
![](images/18.png)

Open and update api.js file with below code

`vim api.js`
![](images/19.png)

![](images/20.png)

-------------

### Create MongoDB database and collection

In Todo directory create and open file .env

`touch .env`

`vi .env`
![](images/21.png)

Add the connection string
![](images/connection.png)



`DB = 'mongodb+srv://<username>:<password>@<network-address>/<dbname>?retryWrites=true&w=majority'`

 Update the index.js file to reflect the use of .env so that Node.js can connect to the database.


 `vim index.js`

update code with below configuration 
 ![](images/24.png)


Start server 

`node index.js`

![](images/25.png)

**Test Backend Code without Frontend using RESTful API**

Using postman to test API

Create a POST request to the API http://<PublicIP>:5000/api/todos

set header key as content-type and value as application/json
![](images/26.png)

Create GET request to API http://<PublicIP>:5000/api/todos
![](images/27.png)

------------

## FRONTEND CONFIGURATION

Use the create-react-app command to scaffold our app

in Todo directory run `npx create-react-app`
![](images/28.png)

**RUNNING REACT APP**

Install concurrently 


`npm install concurrently --save-dev`
![](images/29.png)

Install nodemon

`npm install nodemon --save-dev`
![](images/30.png)

In Todo directory open and edit package.json file changing the script config
![](images/31.png)
![](images/32.png)

In client directory open and edit package.json file
![](images/33.png)

Add the key value pair in the package.json file 
`"proxy": "http://localhost:5000"`


In the Todo directory run `npm run dev`
![](images/35.png)

Add rule for tcp port 3000 in EC2

Applicaition running on port 3000
![](images/36.png)

**Creating React Components**

In SRC folder create folder components

`mkdir components`

create the following files

`touch Input.js ListTodo.js Todo.js`

![](images/37.png)

open and edit input.js

![](images/38.png)

Add the below config
![](images/39.png)
![](images/40.png)

In clinets folder install axios

`npm install axios`
![](images/41.png)

in components file open and add config

`vi listTodo.js`
![](images/42.png)

![](images/43.png)


open todo.js 

`vi todo.js`
![](images/44.png)

Add the below config
![](images/45.png)
![](images/46.png)

In the src folder open App.js file

`vi App.js`

add the below configuration
![](images/48.png)

Open App.css

`vi App.css`

![](images/49.png)

Add below config
![](images/50.png)
![](images/51.png)
![](images/52.png)

open index.css

`vim index.css`
![](images/53.png)

Add the below config
![](images/54.png)

In Todo directory run

`npm run dev`

![](images/55.png)
![](images/56.png)


Reload server on port 3000
![](images/end.png) 

