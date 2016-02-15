# Use the `x` mode to create a file, but only if it doesn’t exist already

You can use the `x` mode to create a new file, but only if it doesn’t already exist. This is called *exclusive creation*:

```python
with open('nonexistentfile', 'x') as f:
    f.write("hello world")
```

This code throws an IOError if you try to write to a file that already exists:

```pycon
>>> with open('existingfile.txt', 'x') as f:
...     f.write("hello world")
...
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IOError: [Errno 17] File exists: 'existingfile.txt'
```

([docs](https://docs.python.org/3.5/library/functions.html?highlight=open#open))