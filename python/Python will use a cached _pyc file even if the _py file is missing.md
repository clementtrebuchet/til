# Python will use a cached *.pyc file even if the *.py file is missing

This one was a bit of a surprise to me.

When CPython runs a file *foo.py*, it compiles the source into byte code before running it.  This byte code is cached in *foo.pyc*, so that it can be used without recompiling again.

When *foo.py* changes, *foo.pyc* is recompiled to match -- that way you don't get stale imports.  So I assumed that if *foo.py* was deleted, Python would ignore *foo.pyc*, and just raise an ImportError.  Nope.

If *foo.py* is missing but there's a *foo.pyc* file in its place, that gets imported instead.  You only get an ImportError if both *foo.py* and *foo.pyc* are missing.

The rationale for this decision, and all the byte code machinery, is in [PEP 3147](https://www.python.org/dev/peps/pep-3147/).  It includes a handy flow chart that explains how Python decides which files to import.

The lesson: beware of stray *.pyc* files hanging around!