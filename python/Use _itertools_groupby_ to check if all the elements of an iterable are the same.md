# Use `itertools.groupby` to check if all the elements of an iterable are the same

We want to check if all the elements of an iterable have the same value. Here’s one way to do it with the itertools module:

```python
from itertools import groupby

def all_equal(iterable):
    g = groupby(iterable)
    return next(g, True) and not next(g, False)
```

Two things that were new to me:

*   `groupby` – it condenses consecutive elements with the same value.  It returns tuples as follows:

    ```pycon
    >>> g = groupby([1, 1, 1, 2, 3, 3, 2, 0])
    >>> for i in g: print(i)
    ...
    (1, <itertools._grouper object at 0x10b9f00d0>)
    (2, <itertools._grouper object at 0x10b9f0150>)
    (3, <itertools._grouper object at 0x10b9f00d0>)
    (2, <itertools._grouper object at 0x10b9f0150>)
    (0, <itertools._grouper object at 0x10b9f0150>)
    ```

    Notice that even elements with a falsey value return a non-empty tuple, so will always evaluate to True.

*   `next` can take an optional default argument, if the iterator is exhausted.  This is analogous to `dict.get()`.

So we use `groupby` to reduce the list into these tuples of consecutive, equal elements.  We grab the first tuple (defaulting to True, so that we cover the empty list). If there's a second tuple to get, the list elements are unequal – so we default to False if we don't find anything.

This is better than using `len(set(iterable)) == 1` for two reasons:

1.  It doesn't rely on the elements being hashable
2.  It doesn't choke on very large iterables

([Raymond Hettinger on Twitter](https://twitter.com/raymondh/status/706646593886248960))