# Use `set -x` or `set -o xtrace` to get a trace of every command in Bash

If you set this flag, then Bash will print every line before executing it. It’s a debug mode that gives you step-by-step debugging of the program. For example:

```text
~> bash -x myscript.sh
+ echo "Hello world"
Hello world
+ echo "I am a script"
I am a script
+ echo

+ echo "Now I'll set a variable"
Now I'll set a variable
+ ANSWER=42
+ echo "The answer is $ANSWER"
The answer is 42
```

You can use `set -x` or `set -o xtrace` at the top of your script, or invoke `/bin/bash` with the `-x` flag, as above or in the shebang.

You can also use `set +x` to turn off debugging, if you only want to debug part of a script.

([source](http://tldp.org/LDP/Bash-Beginners-Guide/html/sect_02_03.html))