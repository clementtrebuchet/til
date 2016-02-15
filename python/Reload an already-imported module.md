# Reload an already-imported module

You can reload a module that you've already imported with the `reload` function.  This has moved around a few times in the various versions of Python:

    reload(foo)             # Python 2

    import imp
    imp.reload(foo)         # Python < 3.4

    import importlib
    importlib.reload(foo)  # Python >= 3.4

[source](http://stackoverflow.com/a/437591/1558022)