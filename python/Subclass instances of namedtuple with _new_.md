# Subclass instances of namedtuple with \__new__

If you want to subclass a namedtuple, you have to use `__new__` instead of `__init__`, and pass `cls` twice. For example:

```python
import collections

Point = collections.namedtuple('Point', 'x', 'y')

class WeightedPoint(Point):
    def __new__(cls, x, y):
        self = super(WeightedPoint, cls).__new__(cls, x, y)
        self.weight = x + y
        return self
```

This is because immutable objects (which includes tuples) are created in `__new__`, not `__init__`.

([source](http://stackoverflow.com/a/3624799/1558022))