# beginner-guide-to-react

## 01-document-create-element

In this blog we are going to see how to create a basic user interface using with vanilla javascript and DOM.

```
<body>
  <div id="root"></div>
  <script type="text/javascript">
    const rootElement = document.getElementById('root')
    const element = document.createElement('div')
    element.textContent = 'Hello World'
    element.className = 'container'
    rootElement.appendChild(element)
  </script>
</body>

```

This is the div that our application is going to be mounted <br>
```<div id="root"></div>```

Here we are accessing root element using document APIs.<br>
```const rootElement = document.getElementById('root')```

Creating a div inside the root element <br>
```const element = document.createElement('div')```

Here we are adding properties to the element <br>

Adding text content to that created div <br>
```element.textContent = 'Hello World'``` <br>
adding class name to the created element <br>
```element.className = 'container'```

Finally we are appending the created element into root element <br>
```rootElement.appendChild(element)```

So Here we learned or brushed up how to create basic user interface using vanilla javascript :)

## 02-react-create-element

In this blog we are going to see how to create a basic user interface using with react and react DOM Library.

```
<body>
  <div id="root"></div>
  <script src="https://unpkg.com/react@16.12.0/umd/react.development.js"></script>
  <script src="https://unpkg.com/react-dom@16.12.0/umd/react-dom.development.js"></script>
  <script type="text/javascript">
    const rootElement = document.getElementById('root')
    const element = React.createElement('div', {
      children: 'Hello World!',
      className: 'container',
    })
    ReactDOM.render(element, rootElement)
  </script>
</body>
```

React.js sources were added from [unpkg](https://www.unpkg.com) to add react to our page <br>
We need to include the react source in order to work in react. Below scripts is used to create react element.<br>
```<script src="https://unpkg.com/react@16.12.0/umd/react.development.js"></script>```<br>
This script is used to render those element to the page<br>
```<script src="https://unpkg.com/react-dom@16.12.0/umd/react-dom.development.js"></script>```<br>

In previous blog we used document api to create our div. Instead here we are using ```React.createElement```. ```React.createElement``` accepts first argument to specify type of element.  Another difference instead of using ```textContent``` we are using ```children``` to add text and ```className``` to add class to the element

```
const element = React.createElement('div', {
  children: 'Hello World!',
  className: 'container',
})
```

Here we have another way to write the same children as a third argument to ```React.createElement``` by simply providing value for the children ```prop``` those are functionally equivalent

```
const element = React.createElement('div', {
  className: 'container',
}, 'Hello World!', ', Nice to meet you :)')
```
#### OR

Use this to the children props directly like specify as array as example below
```
const element = React.createElement('div', {
  children: ['Hello World!', ', Nice to meet you :)']
  className: 'container',
})
```

And it is also give flexibility to create additional react element to be children. Here in children props ```React.createElement``` includes type of ```span``` and props are null and the children are in the array of hello world!
```
const element = React.createElement('div', {
  children: React.createElement('span', null, 'Hello', ' World :)'),
  className: 'container',
})
```

Atlast we are rendering the element to the root element using ```ReactDOM.render()```
```ReactDOM.render(element, rootElement)```

## 03-jsx
In this blog we are going to see how to use jsx in our react application. <br>

```
<body>
  <div id="root"></div>
  <script src="https://unpkg.com/react@16.12.0/umd/react.development.js"></script>
  <script src="https://unpkg.com/react-dom@16.12.0/umd/react-dom.development.js"></script>
  <script src="https://unpkg.com/@babel/standalone@7.8.3/babel.js"></script>
  <script type="text/babel">
    const rootElement = document.getElementById('root')
    const element = <div className="container">Hello World</div>
    ReactDOM.render(element, rootElement)
  </script>
</body>
```

Using create react element in this wat works out just fine. But it is not entirely ergonomic. It is not that most of community creates React elements.

```
const element = React.createElement('div', {
  children: 'Hello World!',
  className: 'container',
})
```

Most of the community is using JSX. Which is HTML like syntax in our Javascript. So if I were to create the same React element using JSX. I would make like below. We'll say element is a div. Our children are Hello World!. Then we add className which is prop. That'll go as an attrubute on our div here with className="container" <br>

```const element = <div className="container">Hello World</div>``` <br>

Most importantly browser doesn't understand this natively. We need to compile this to something that the browser can understand. That where Babel comes in. Babel is a javascript compiler supporting the next generation of javascript as well as non standard feature like JSX. Here you can use Babel [try it out](https://babeljs.io/repl) page to see our code being compiled to something very familiar to us and the browser. I would like you to spend sometime in this tool. Understanding how JSX is compiled will make you effective at using JSX.

In a typical application you are going to be using a tool that will use to Babel to compile JSX to Javascript for you. For our purposes we are going to use Babel in the browser to get this compiling right in here without having to install any other tools. This below script tag here to include Babel standalone. That will compile any script tag that has a type ```text/babel```. Then it will create the new script with the compiled code type as ```text/javascript``` so that browser can evaluate it.

``` <script src="https://unpkg.com/@babel/standalone@7.8.3/babel.js"></script>```
