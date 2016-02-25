# How to remove duplicate dicts from a list

You have a list of dictionaries, but you know some of them might be the same. How do you only get the unique dicts?

Normally we use `set()`, but that won’t work because dicts aren’t hashable. Instead, here’s a one-liner that expresses the basic idea:

```python
[dict(t) for t in set([tuple(sorted(d.items())) for d in l])]
```

Convert the items in each dict to a tuple of tuples (sorting to ensure you get consistent ordering). Since tuples are hashable, you can remove the duplicates with `set`, and then rebuild the dicts with `dict`.

([source](http://stackoverflow.com/a/9427216/1558022))