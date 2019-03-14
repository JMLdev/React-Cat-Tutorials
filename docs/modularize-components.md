---
title: Component Modularization
layout: default
---

# Reusing Components


Last lesson we identified that a few page components will probably be used more than once. The heading is going to appear on every page and has Some markup and styling on it. We don't really want to copy this across all the pages, so it's a perfect candidate for a component. The graph is probably going to need some logic on it, and we don't necesarily want the app file cluttered with that logic, so it'll be a component too.


## Creating Graph Component

Lets start with the graph. Create a folder in the root of your project and call it `Components`. Inside the `Components` folder, create a `Graph.js` file. This will hold the code for our graph. It's a pretty simple file. You'll import React and some Reactstrap components and then it's pretty much a straight copy/paste from the [Reactstrap docs page for the Progress Component](https://reactstrap.github.io/components/progress/).

```javascript
import React, { Component } from 'react';
import { Row, Col, Progress } from 'reactstrap';

 class Graph extends Component {
    render() {
        return (
            <Row style={marginBottom: '24px'}>
                <Col>
                    <h2>
                        Status so far:
                    </h2>
                    <div>Cute</div>
                    <Progress value={70} />
                    <div>Crap</div>
                    <Progress value={20} color={"danger"} />
                </Col>
            </Row>
        )
    }
}

 export default Graph;
 ```
That's pretty much it. Lets create the Heading now.

## Creating the heading

Go ahead and create another file in the `Components` folder you created in the steps above. You will name it `Heading.js`. This one is cooler, because you're actually going to get to use props for the first time!

Paste the following code into your newly created `Heading.js` file.

```javascript
import React, { Component } from 'react';
import { Row, Col } from 'reactstrap';

 export class Heading extends Component<any> {

     render() {
        return (
            <Row style={marginBottom: '64px', marginTop: "24px"}>
                <Col>
                    <h1>
                        {this.props.heading}
                    </h1>
                </Col>
            </Row>
        )
    }
}

 export default Heading; 
```

So once again, you're importing React and Component, importing the Reactstrap components you need, and then laying down some JSX inside the `render()` method of the React class. Except this time, you made a prop! Inside the h1 tag is `{this.props.heading}`. That's a named prop. `this` means it refers to itself. It's going to display whatever `this` instance of the component inherits from it's calling parent. To clarify, you will pass a prop value down to the component when you call it, and `this` instance of the component will use that value when rendering. `props` just tells react that 'hey, there's a variable here'. Finally 'heading' is the name of the prop. That's how you'll call it. We're going to call it on every page moving forward, but here's a quick example of how it will be used `<Heading heading="Hello World" />`. This example will render a Reactstrap row and column and an h1 tag with the contents being a string that says "Hello World". Cool. Right? You're still with me? Cool!

## Update the Homepage

Alright! Now that you've created a couple of components, go ahead and use them. Open `App.js` up again and add the following code underneath the line where you call in the reactstrap components.

```javascript
import Graph from './Components/Graph';
import Heading from './Components/Heading';
```

Boom! You now have access to the created components. Update the `App.js` render markup to use the components instead of the static JSX. 

```javascript
<Row style={ marginBottom: "64px", marginTop: "24px" }>
    <Col>
        <h1>Cats, cute or crap?</h1>
    </Col>
</Row>
```

gets replaced with 

```javascript
<Heading heading='Cats, cute or crap' />
```

Save the file and check your page. It should look exactly the same as before. Lint is probably complaining about an unused variable now, so go ahead and rectify that. Replace 

```javascript
<Row style={ marginBottom: "24px" }>
    <Col>
        <h2>Status so far:</h2>
        <div>Cute</div>
        <Progress value={70} />
        <div>Crap</div>
        <Progress value={20} color={"danger"} />
    </Col>
</Row>
```

with `<Graph />`. This component doesn't currently accept any props, so it's just a simple component call. 
