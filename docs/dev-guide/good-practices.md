# Good Practices

## Node Packagges

It is important to keep the number of node packages as few as possible, so that we can avoid unnecessary dependencies. If there is one that makes the job easier and that is foreseeable to be used in the future, then it is recommended.


## Performance

### Transitions

(avoid using transition: all, specify the properties that need transition)
(avoid transitions on properties like height, use framer motion instead)

### Event Listeners

Having too many event listeners on your website can negatively impact its performance and user experience. To avoid this, you should aim to minimize the number of event listeners and use techniques such as event delegation and removing unnecessary event listeners. You can also use browser developer tools to identify and optimize the usage of event listeners on your website.
