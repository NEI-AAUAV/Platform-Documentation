# Good Practices


## Linting


## Testing

## Performance

### Transitions

(avoid using transition: all, specify the properties that need transition)
(avoid transitions on properties like height, use framer motion instead)

### Event Listeners

Having too many event listeners on your website can negatively impact its performance and user experience. To avoid this, you should aim to minimize the number of event listeners and use techniques such as event delegation and removing unnecessary event listeners. You can also use browser developer tools to identify and optimize the usage of event listeners on your website.


## Conditional Rendering

Always use ! and !! to convert to boolean. This avoids rendering 0, null, undefined, etc.
