
![](https://github.com/LewNic1/Electron/blob/master/electron.png)

# Concept
Electron is an open-source framework developed and maintained by GitHub. Electron lets you write cross-platform desktop applications using JavaScript, HTML and CSS. Electron uses Chromium for the frontend and Node.js for the backend so you can build your applications. 

![](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ0uennhqsc6wLg3Jkt7u-5WcV-eD4vZe1QoxiN4pY96lhSdXFn)

<!-- Code Snippet to write Hello world in Electron -->
 This is main.js file
Modules to control application life and create native browser window
const {app, BrowserWindow} = require('electron')

 Keep a global reference of the window object, if you don't, the window will
 be closed automatically when the JavaScript object is garbage collected.
let mainWindow

```function createWindow () {
  Create the browser window.
  mainWindow = new BrowserWindow({
    width: 1000,
    height: 600,
    webPreferences: {
      nodeIntegration: true
    }
  })
```
 `` and load the index.html of the app.
  mainWindow.loadFile('index.html')
``
   Open the DevTools.
  mainWindow.webContents.openDevTools()

   Emitted when the window is closed.
 ``` mainWindow.on('closed', function () {
     Dereference the window object, usually you would store windows
   #  in an array if your app supports multi windows, this is the time
    // when you should delete the corresponding element.
    mainWindow = null
  })
}
```
 This method will be called when Electron has finished
 initialization and is ready to create browser windows.
 Some APIs can only be used after this event occurs.
app.on('ready', createWindow)

```Quit when all windows are closed.
app.on('window-all-closed', function () {
  # On macOS it is common for applications and their menu bar
  # to stay active until the user quits explicitly with Cmd + Q
  if (process.platform !== 'darwin') app.quit()
})
```
app.on('activate', function () {
  ## On macOS it's common to re-create a window in the app when the
  ## dock icon is clicked and there are no other windows open.
  if (mainWindow === null) createWindow()
})
```
# In this file you can include the rest of your app's specific main process
# code. You can also put them in separate files and require them here.

``` This is a package.json file 
{
  "name": "electron-quick-start",
  "version": "1.0.0",
  "description": "A minimal Electron application",
  "main": "main.js",
  "scripts": {
    "start": "electron ."
  },
  "repository": "https://github.com/electron/electron-quick-start",
  "keywords": [
    "Electron",
    "quick",
    "start",
    "tutorial",
    "demo"
  ],
  "author": "GitHub",
  "license": "CC0-1.0",
  "devDependencies": {
    "electron": "^4.1.3"
  }
}
```

This is a index.html file
```<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <title>Hello World!</title>
  </head>
  <body>
    <h1>Hello World!</h1>
    <!-- All of the Node.js APIs are available in this renderer process. -->
    <!-- We are using Node.js <script>document.write(process.versions.node)</script>,
    Chromium <script>document.write(process.versions.chrome)</script>,
    and Electron <script>document.write(process.versions.electron)</script>. -->
    <h1>We are on week 12!! I can't belive it.</h1>

    <script>
      // You can also require other files to run in this process
      require('./renderer.js')
    </script>
  </body>
</html>

```
## Our Findings
We found Electron to be familiar to us because it uses node.js and the package framework made it easy to set up a project. We would recommend it for those who want to build desktop applications. We found the benefit of only working on one browser and one code base to be helpful. We would consider using it in future projects to build desk top applications. Electron will increase one's knowledge of knowing another framework.

```
## Sources
Video explaining Electron thoroughly from their site
[Electron](https://www.youtube.com/watch?v=8YP_nOCO-4Q&feature=youtu.be)
