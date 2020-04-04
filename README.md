# beginner-guide-to-react

## 01-document-create-element

In this blog we are going to see how to create basic user interface using with vanilla javascript and DOM.

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
