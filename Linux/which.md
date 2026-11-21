The **`which` command** in Linux ==locates and prints the **full path of an executable file** associated with a given command name==. It works by scanning the directories listed in your system's `PATH` [[environment variable]] in order and returning the first match it.

**Check which executable a command uses**

```
which python3
```

Example output:

```
/opt/homebrew/bin/python3
```

Other examples:

```
which git
which node
which java
```

These help answer: “Which installed version am I running?”

**3. Find multiple versions of a command**

```
which -a python3
```

Example output:

```
/opt/homebrew/bin/python3
/usr/bin/python3
```