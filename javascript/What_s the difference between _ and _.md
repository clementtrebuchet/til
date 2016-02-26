# What’s the difference between == and ===?

The former does type comparison, whereas the latter doesn't. For example:

```javascript
2 == 2    // true
2 == "2"  // true
2 === 2   // true
2 === "2" // false
```

([source](http://stackoverflow.com/a/405710/1558022))