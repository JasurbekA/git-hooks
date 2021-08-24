# git-hooks

In this repo I will show how to integrate git hooks 
1. Make sure you init git for your project folder
2. create file (name could be anything, but I prefer name should speak for itself) inside YOUR_PROJECT/.git/hooks
3. Specify what you want to do before pushing your code to remote branch

Here is the example (I wanted to run tests, but you can run other commands like checking code format using ktlint)

```
#!/bin/bash


echo "Running git pre-commit hook"

./gradlew test

RESULT=$?

# return 1 exit code if running checks fails
[ $RESULT -ne 0 ] && exit 1
exit 0
```

4. Save the file and make sure the file is executable (you can run ```chmod a+x ./.git/hooks/FILE_NAME``` to make file as executable file)

Now come to the root project and run ```git push``` 
