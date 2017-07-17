# How to: Setup a React development environment on Mac

Guide to installing the tools required to run React+Webpack (via create-react-app) on Mac

> **Attention! Before getting started!** This guide was tested on Mac OS 10.11 using Node v6.11.1 and npm 5.3.0. 

## Steps

1. Running the Terminal.app and Installing Homebrew
2. Install Node.js
3. Upgrading **npm**
4. Installing **create-react-app**
5. Creating a basic React application
6. Starting your React application
7. Editing your React application 
8. Releasing your React application to the public

---

### 1. Opening Terminal.app

Using Spotlight (option+space), search for **Terminal.app** and hit _return_ top open it.

Next, install XCode's command line tools by typing in:

```bash
xcode-select --install
```

Once this is installed, you can move on to...

---

### 2.  Install Node.js via nvm

[NVM](https://github.com/creationix/nvm) is a version manager that lets you easily run multiple versions of Node on MacOS or Linux. Run this command to install nvm: [Additional info about isntall nvm here](https://nodesource.com/blog/installing-node-js-tutorial-using-nvm-on-mac-os-x-and-ubuntu/).

```bash
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.0/install.sh | bash
```

This will install NVM. Once it is done, verify that everything is installed correctly. In your terminal, type in:

Now we'll install the the LTS (long-term service) version of Node via NVM. Run

```bash
nvm install --lts
```

---

### 3. Installing create-react-app

There is a boilerplate already written for react - it is called _create-react-app_. It is available, like many other scripts, on the _node package manager (npm)_. We can install it using the `npm i` command again. Run the following code in your terminal:

```bash
npm i -g create-react-app
```

This can also take a few moments - `npm` is having to install React and other tools on your computer. Once complete, you'll see output similar to this:

```bash
$ npm install create-react-app -g
/Users/James/.npm/create-react-app -> /Users/James/.npm/node_modules/create-react-app/index.js
+ create-react-app@1.3.3
updated 1 package in 41.553s
```

---

### 4. Creating a basic React application

> You're over halfway there! Keep it up!

It is time for you to finally create a React application from the `create-react-app` boilerplate. When you use `create-react-app`, you should specfiy a name for your application. It will create the following file structure for you in a folder with the name of your app. That structure looks like this:

```bash
├── README.md
├── package.json
├── public
│   ├── favicon.ico
│   └── index.html
└── src
    ├── App.css
    ├── App.js
    ├── App.test.js
    ├── index.css
    ├── index.js
    └── logo.svg
```

The `index.html` has all of the App.js code _injected_ into it using the tools that `create-react-app` provides. It even creates start Javascript and CSS files for you. **This should make you feel awesome!**

Time for you to try it out. Run:

```bash
create-react-app hi-react
```

This creates a folder wherever you are called `hi-react`. _create-react-app_ tells you where this is installed so you can easily find it to open in your text editor. Once complete, you should see the following (or similar):

```bash
$ create-react-app hi-react
Creating a new React app in C:\Users\James\hi-react.

Installing packages. This might take a couple of minutes.
Installing react, react-dom, and react-scripts...

+ react@15.6.1
+ react-dom@15.6.1
+ react-scripts@1.0.10
added 1205 packages in 54.568s

Success! Created hi-react at C:\Users\James\hi-react
Inside that directory, you can run several commands:

  npm start
    Starts the development server.

  npm run build
    Bundles the app into static files for production.

  npm test
    Starts the test runner.

  npm run eject
    Removes this tool and copies build dependencies, configuration files
    and scripts into the app directory. If you do this, you can’t go back!

We suggest that you begin by typing:

  cd hi-react
  npm start
```

---

### 5. Starting your React application

_create-react-app_ includes a web server to test your app on. You'll need to _change directory_ (cd) into your applicaton to run it. Do this:

```bash
cd hi-react
```

And then run:

```bash
pwd
```

You should see that you your `hi-react` folder:

```bash
$ pwd
/c/Users/James/hi-react
```

Now, start your application using `npm` --

```bash
npm run start
```

You'll be informed that your application is running. It _should_ also open up a new web browser pointing to the correct (but temporary) URL.

```bash
$ npm run start

> hi-react@0.1.0 start C:\Users\James\hi-react
> react-scripts start

Starting the development server...

Compiled successfully!

You can now view hi-react in the browser.

  Local:            http://localhost:3000/
  On Your Network:  http://192.168.56.1:3000/

Note that the development build is not optimized.
To create a production build, use npm run build.
```

You can also browse tothe _local_ address provided. In this case, you could point your browser to [http://localhost:3000/](http://localhost:3000/)

You should see the React starter page.

![react.PNG](react.PNG)

---

### 6. Editing your React application

You'll notice that you're encouraged to edit the `src/App.js` file. This is where you can shine! For now, just edit the text in front of you and hit save in your editor of choice. Refresh your application in the browser and you'll see your changes are updated.  

You should also take a moment to install the [React Developer Tools Extension for Chrome](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en). 

Once they are installed, you will have a new _tab_ under DevTools to the far right. If you select it, you can see React components clearly.

![devtoolsreact.PNG](devtoolsreact.PNG)

> If you ever need to stop your server, press `control + c` at the same time. This will stop _any_ terminal process.

---

### 7. Releasing your React application to the public

Once you are satisfied with your application, it is time to bundle your code together ready for the web. `create-react-app` will bundle your code, remove whitespace, obfuscate it so it is harder for others to read, and make it take up less space. Press `control + c` at the same time to exit your React server if you have not already. Once you have done that, you will see that you can enter more commands in your terminal. Run the following:

```bash
npm run build
```

This process can take a few moments. Once it is complete, the _entire_ contents of your website will be available in the **build** subdirectory of your project. It will contain the following files and folders:

```bash
asset-manifest.json  favicon.ico  index.html  manifest.json  service-worker.js  static/
```

All of these files and folders can then be uploaded to a website for production or be distributed to clients for a final release.


*fin*
