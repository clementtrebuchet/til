# Use named capturing groups in regexes

If I want to get some information out of a regex, I can use capturing groups:

```python
import re
version = re.compile('V([\d+]).([\d+])')

m = version.match('V2.3')
major = m.group(1)
minor = m.group(2)
```

But in a large regular expression, it can be easy to lose track of the numeric indices.  And reading the regex alone, it's not easy to see what each part of the regex means.

Python supports *named* capturing groups.  This seems like a really useful way to make regexes more readable.  For example:

```python
import re
version = re.compile('V(?P<major>[\d]+)(.(?P<minor>[\d]+))?')

m = version.match('V2.3')
major = m.group('major')
minor = m.group('minor')
```

I can still use the numeric indices (as in the first example), so this doesn't break old code -- it's just a nice extra.


