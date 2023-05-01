# Deploy-multipleProjects
## node.js deployment
### Step 1 - Install Nodejs
1.curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -<br/>
2.sudo apt-get install -y nodejs<br/>
3.node --version && npm --version<br/>
### Step 2 - Creating a sample nodejs file
1.Create a sample app {sudo vi app.js}<br/>
2.const express = require('express')<br/>
const app = express()<br/>
const port = 3000<br/>

app.get('/', (req, res) => {
  res.send('Hello World!')
})<br/>

app.listen(port, () => {
  console.log(`Example app listening at http://localhost:${port}`)
})<br/>
