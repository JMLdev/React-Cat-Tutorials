---
layout: default
---

# Index Structure Overview

Okay, I lied, we're not quite ready to start writing code yet. First, lets explore the project as it currently is. 

Open the file tree and look at the src folder. The index.js file is the outermost part of the React structure. It is the shell that serves everything else. Unless you've changed something, your code should look like this

```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';

import "bootstrap/dist/css/bootstrap.min.css";
import * as serviceWorker from './serviceWorker';

ReactDOM.render(<App />, document.getElementById('root'));

// If you want your app to work offline and load faster, you can change
// unregister() to register() below. Note this comes with some pitfalls.
// Learn more about service workers: http://bit.ly/CRA-PWA
serviceWorker.unregister();
```

At the top of the file are the imports, this is where it calls in other resources, components, modules, and everything it needs to load the full application. The 

```javascript
ReactDOM.render(<App />, document.getElementById('root'));
```

line takes everything in the `<App />` component and renders it to the DOM element with an ID of `root`. This is a simple named div in the `index.html` file in the public folder of your repo. You can open `public/index.html` and see that it is nothing more than an empty div. This is because React renders everything asyncronously and dynamically when the application loads, following all the instructions in your methods, functions, classes, and modules.

## App.js Overview

Since `index.js` is not doing anything more than calling the `<App />` component, lets open that now. You can see in the code that `App` is imported from `./App`, so go ahead and open that file. There's a bit more code in the `App.js` file, but it is still pretty basic. Here is an overview of what it is doing, in case you haven't figured it out yet. 

1. Importing React modules from `'react'`
2. Importing an svg image as `logo`
3. Importing some CSS rules from `App.css`
4. Defining a React Class as `App`
5. Using basic JSX markup to create the module's HTML structure
6. Exporting the Component as the default component for the file

Now the `App` component can be imported and called by any other React page, but in this case, it is only called by the `index.js` file. So as of now, the hierarchy for this application is `index.js` as the outermost parent, then `app.js` as it's child. For the most part, `App` will be used as the top-level parent for this application. This is important, since React has [strict hierarchy rules](https://reactjs.org/docs/lifting-state-up.html) for `state` and `props`. It's probably a bit too early to dive into those concepts yet, so just take the basics and move on. It should all start making more sense as you work through the course. 

Lets update the homepage to be more representative of our needs. Continue to the next lesson.