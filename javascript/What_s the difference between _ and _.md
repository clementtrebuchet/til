# What’s the difference between == and ===?

The first tests for equality and coerces the types to fit. The latter also checks whether they're the same type. For example:

```javascript
2 == 2    // true
2 == "2"  // true
2 === 2   // true
2 === "2" // false
```

They can return different results if the objects under comparison are different types. In the case where the two objects are different types, `===` will be faster because it skips the type coercion – but the performance difference is usually negligible.

([source](http://stackoverflow.com/a/359509/1558022))
