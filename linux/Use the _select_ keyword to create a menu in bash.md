# Use the `select` keyword to create a menu in bash

You can use the `select` keyword to create simple menus in bash. The syntax is the same as a for loop:

```bash
select item [in list]
do
    some_work_with item
done
```

It creates a menu for each item in the list, with numbers for each chocie, and prompts the user for a number. It then executes the body of the loop with the given choice.

Note that it will keep prompting the user for a new choice every time the loop repeats, so you need an explicit `break` statement if you don’t want the user to go around forever.

> **Example.** The select loop:

> ```bash
select fruit in apple banana cherry
do
  echo "You picked some $fruit”
done
```

> produces the menu:

> ```
1) apple
2) banana
3) cherry
#?
```

You can customise the prompt by setting the `PS3` environment variable.