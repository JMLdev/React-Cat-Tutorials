---
title: Introduction
layout: default
---

# App Homepage Concepts

In the next lesson we're going to add some JSX to create a homepage that matches our site intent. We want to let users know what the site is for, and give them options to navigate to the pages were the action actually takes place.

We're not going to dive too heavily into React's complexities yet, since our home page won't have any fancy functionality at that point, but we will cover some important React concepts. 

## Intro to JSX

React uses a hybrid syntax called JSX. It is a mixture of HTML and JavaScript. This allows us to easily add logic and functionality to markup, without having to write confusing concatination functions.

Here is a simple example of JSX in use

```javascript
const name = 'Josh Perez';
<h1>Hello, {name}</h1>;
```

In this particular example, the `{name}` portion of the markup will render out to the browser as Josh Perez. Pretty cool, right? Although this is a simple example, there is a lot of power in this syntax. It frees up some mental overhead when structuring the DOM, so you can focus more on the logic and less on the markup. This is an important concept in React. If you don't quite grasp it, then please read more about JSX on the [official documentation page](https://reactjs.org/docs/introducing-jsx.html). If you've used templating frameworks before, such as Handlebars.js, then you're already familiar with this concept, but in React, the syntax comes with the full power of JavaScript.

## Introduction to Components

Another important concept in React is components. Components are the building block of your application. If you're a front-end developer, then think of them as you would what you've traditionally called a 'component'. They're small chunks of a website that can be reused throughout the site. Unlike your 'traditional component', they can be completely self-contained. What this means is that you can embed a component with all of it's associated functions, methods, and even styling, so that it is truly portable. If you're a back-end developer or engineer, then you'd probably compare a component to a Class. Matter of fact, that's exactly what they're described as in the syntax. 

#### Component Example

Consider the following code

```javascript
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

It's extending our earlier example and encapsulating it into a component. Now you can call `<Welcome />` Anywhere else in your app (as long as you've imported it - more on this later) and it'll render out `<h1>Hello Name</h1>` to the DOM, where name is whatever you've defined it as. Pretty cool. Right?

Ready to actually write some code? Well lets get to it in the next lesson.