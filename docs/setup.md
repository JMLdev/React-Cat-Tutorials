---
title: Setup Instructions
layout: default
---

# Project setup

Once your computer has all the [required dependencies](/dependencies.md) you are ready to begin.

## Create a React Application

There's a great package that will do most of the heavy lifting for you, when Starting a new React.js project. It won't always fit your needs, but it is ideal for most smaller projects. You will use the command line interface for this step, so either open a command prompt (terminal) in your project folder location, or press `ctrl+`` to open the terminal in Visual Studio code. 

Once Terminal is open, type the following, where 'my-app-name' is whatever you want the app and parent folder to be called.

```
npx create-react-app my-app-name
```

This will isntall React and all of it's associated file requirements, webpack, a local test server, and babel. Once it is finished, type 

```
cd my-app-name
```

then feel free to look around. Don't open `node_modules` though, there's about a billion folders in there.

Your core site files reside in the `src` folder, and the `public` folder hosts the shell files for the web browser. When you are finished looking around type the following into the browser

```
npm start
```

If you've done everything correctly up until now, npm will spin up a development browser and launch your brand new React app. If it doesn't automatically load in the browser, ctrl+click one of the links in the terminal output. Once you see the spinning logo, you can be sure you are on-track. Give yourself a pat on the back, but don't close terminal.

### Add Reactstrap

Since this tutorial is really about learning react, and not about learning basic website development, we're going to use [Reactstrap](https://reactstrap.github.io/) to create our web pages. Reactstrap is [Bootstrap 4](https://getbootstrap.com/docs/4.0/getting-started/introduction/)'s React.js port. It will allow us to leverage an existing grid and components so we only have to implement minimal styling considerations.

In the same terminal as above, type

```
npm install bootstrap --save
npm install --save reactstrap react react-dom
```

This will install Bootstrap, update React - even though we don't really need to since we just installed it - install the react-dom if you don't already have it, and most importantly it installs Reactstrap. The `--save` flag updates your package.json file. All of these files will be maintained by NPM and stored under the `node_modules` folder. You don't need to mess with them.

None of this actually imports the Bootstrap styles to your app though, so we'll do that now. Open the `src/index.js` file and paste the following code under the second to last import, with a line break above it. The idea here is to group like imports together, so they're easily readable. 

```
import 'bootstrap/dist/css/bootstrap.min.css';
```

The top of your index.js file should now look like this. We've grouped React stuff together, and then anciliary stuff at the end.

```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';

import "bootstrap/dist/css/bootstrap.min.css";
import * as serviceWorker from './serviceWorker';
```

That's it! You have a fully functional React.js application that is leveraging Reactstrap for styling and component markup. Go ahead to the next lesson to start building. 