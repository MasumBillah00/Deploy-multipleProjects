### -----Deploy-multipleProjects-----
# node.js deployment
### Step 1 - Install Nodejs
1.curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -<br/>
2.sudo apt-get install -y nodejs<br/>
3.node --version && npm --version<br/>
### Step 2 - Creating a sample nodejs file
1. sudo vi app.js--{Create a sample app}<br/>
2.{Sample Project}const express = require('express')<br/>
const app = express()<br/>
const port = 3000<br/>

app.get('/', (req, res) => {
  res.send('Hello World!')
})<br/>

app.listen(port, () => {
  console.log(`Example app listening at http://localhost:${port}`)
})<br/>
3.npm install express<br/>
4.node app.js--{Run node.js}<br/>
5.sudo npm i pm2 -g --{nstall and use pm2 as a process manager}<br/>
6.pm2 start app.js --{Start the application} <br/>
### Step 3 - Configuring Nginx as a reverse proxy
1.sudo apt install nginx--{Install Nginx}<br/>
2.sudo vi /etc/nginx/sites-available/nodeApp--{create a conf file for our Nodejs app }<br/>
3.server{
  server_name "ip address";

      location / {
        proxy_pass http://localhost:3000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
    }
}<br/>
4.sudo ln -s /etc/nginx/sites-available/nodeApp /etc/nginx/sites-enabled--{Activate command}
### Step 4 - Remove Nginx Default App
# React.js Development
### Step 1 - Install Node.js and npm 
1.sudo apt update<br/>
sudo apt install nodejs<br/>
sudo apt install npm<br/>
### step 2 - Create a new directory for project
mkdir hello-world<br/>
cd hello-world<br/>
### Step 4 - Initialize a new npm project & Install React.js and React-DOM 
npm init -y<br/>
npm install react react-dom<br/>
### Step 5 - Create a new file called 'index.js' in the 'src' directory
mkdir src<br/>
cd src<br/>
touch index.js<br/>
### Step 6 -Open the index.js file in a text editor 
"import React from 'react';<br/>
import ReactDOM from 'react-dom';<br/>

const Hello = () => {
  return <h5>Hello World!</h5>;
};"<br/>

ReactDOM.render(<Hello />, document.getElementById('root'));<br/>
### Step 7 - Create a new file called index.html in the root
cd ..<br/>
touch index.html
### Step 8 - Open the index.html file in a text editor 
"<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Hello World</title>
  </head>
  <body>
    <div id="root"></div>
    <script src="./dist/bundle.js"></script>
  </body>
</html>"












