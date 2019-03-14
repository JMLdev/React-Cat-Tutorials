---
title: Creating the Homepage
layout: default
---

# Create Home Page

Wewt wewt! Finally time to add some code. This will mostly just be JSX without any logic at this point, but every app starts somewhere. You may remember a few lessons ago, I talked about making our homepage more representative of the apps purpose. Here's a list of what I want on the homepage as a nice starting point for our app. 

* Heading
* Graph of progress
* A paragraph describing the purpose of the site
* A couple of cards describing each page we will have, with a link to the page

That's pretty much all we need. Fortunately, the nice community behind Bootstrap have already written all the CSS we need to make the page pretty. Since there's no sense in reinventing the wheel, lets go ahead and import Reactstrap. 

## Importing Reactstrap Components

Open the `App.js` file in the root of your project and delete the `import logo from './logo.svg';` line, since we aren't going to use that logo, and then add the following code at the top, right underneath `import './App.css`.

```javascript
import { Container, Row, Col, Card, CardImg, CardText, CardBody,
  CardTitle, CardSubtitle, Button, Progress } from 'reactstrap';
```

The above code is going to find `reactstrap` in the node_modules folder and then import the components we specified. If you take  a look at what we're importing, you'll see it's pretty much everything from our bullet list of needed DOM components. 

## Calling Components

Once you've imported the Reactstrap components, then it's pretty easy to use them. The syntax is `<Component props='whatever' />`. Notice the code is self closing, and capitalized. Component would be the name of the component, and if the component accepts props, you call them inline for simpler components like in our example. Remember, props are variables values passed into the component itself. 

## Putting it all together. 

If you aren't familiar with Bootstrap, and you want to learn more, [then please head over to their website](https://getbootstrap.com/). They have excellent documentation and can explain their framework much more efficiently than I can. Assuming you're at least somewhat familiar with Bootstrap, and understand the component concept, the homepage code will make sense to you. Here's what I came up with. Replace everything inside of the `return()` function inside of the App component with the following code.

```javascript
<Container>
    <Row style={marginBottom: '64px', marginTop: "24px"}>
        <Col>
            <h1>
                Cats, cute or crap?
            </h1>
        </Col>
    </Row>
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
    <Row>
        <Col>
            <p style={marginBottom: '24px'}>Cat ipsum dolor sit amet, sleep but scratch my tummy actually i hate you now fight me. Sleep everywhere, but not in my bed flop over scratch my tummy actually i hate you now fight me curl into a furry donut. Chase after silly colored fish toys around the house scratch my tummy actually i hate you now fight me and human clearly uses close to one life a night no one naps that long so i revive by standing on chestawaken! </p>
        </Col>
    </Row>
    <Row>
        <Col sm={12} md={6}>
            <Card>
                <CardImg top width="100%" src="https://placekitten.com/318/180" alt="Cat image" />
                <CardBody>
                    <CardTitle>Cute or Not?</CardTitle>
                    <CardSubtitle>Vote on pictures of cats</CardSubtitle>
                    <CardText>Cute, or the next ugly cat meme? You be the judge. Browse through images of cats and determine which are cute and which are crap.</CardText>
                    <Button color="primary">Vote Now</Button>
                </CardBody>
            </Card>
        </Col>
        <Col sm={12} md={6}>
            <Card>
                <CardImg top width="100%" src="https://placekitten.com/318/181" alt="Cat image" />
                <CardBody>
                    <CardTitle>Index of Results</CardTitle>
                    <CardSubtitle>See a list of kitties.</CardSubtitle>
                    <CardText>How did they fare? Find out now. Easily browse the kitty cats and see their ranking.</CardText>
                    <Button color="success">View List</Button>
                </CardBody>
            </Card>
        </Col>
    </Row>
</Container>
```

Save the file and check your browser. You should have a pretty decent looking homepage at this point. Of course, nothing actually does anything, but we'll fix that later. 

When you look at the page, you can quickly see a few parts of the page that are reusable. Continue to the next lesson to modularize some page elements. 