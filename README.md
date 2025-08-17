# my-app1
 ┣ package.json
 ┣ server.js
 ┗ render.yaml   (اختياري لتهيئة Render)
{
  "name": "my-app",
  "version": "1.0.0",
  "main": "server.js",
  "scripts": {
    "start": "node server.js"
  },
  "dependencies": {
    "express": "^4.18.2"
  }
}
const express = require("express");
const app = express();
const PORT = process.env.PORT || 3000;

app.get("/", (req, res) => {
  res.send("🚀 Hello World from Render!");
});

app.listen(PORT, () => {
  console.log(`Server running on port ${PORT}`);
});
services:
  - type: web
    name: my-app
    env: node
    buildCommand: "npm install"
    startCommand: "npm start"
    plan: free
