# This week's Lab!
## Objective:
Get used to creating new scripts, using the /tmp directory,
and creating more involved decisions. The `/tmp/` directory is the temporary directory, and is
regularly cleaned by linux during things such as when the system reboots. Its a useful place to insert files you don't plan to keep!

Furthermore, we're going to improve our own command line capabilities by looking at the .bashrc file, a way to customize our environment.

## Step 1) Getting Started
1. This time, we will, not create a new folder. Instead, enter `~/data1201/labs`.
2. Inside of labs, create a file named __setup.sh__.
    1. Make the file executable using `chmod`
    2. Remember to start the shell script with `#!/bin/bash`
    3. Have it create a safe temporary file using `mktemp`, and save it into a variable by using a subshell!
    4. Use `curl` with an output of the temporary file, and the target url being the .zip version of this directory!
        1. Use the `-L` flag to follow redirects that git provides.
        2. The output of curl should be saved using `-o` to the temporary file in the local variable.
        3. The .zip is located at https://github.com/skpomerv/data1201/archive/refs/heads/main.zip
    5. Finally, use `unzip` to extract the contents of the temporary file to `~/data1201/labs`
    6. The directory unzipped is named `data1201-main`, so rename it using `mv` to be named `lab9`.
    
3. Once complete, run the file, then __move the file into the lab9 folder__.

## Step 2) Fancifying your Environment!
You can customize your bash shell with shortcuts to commands, as well as make changes for the environment.

For now, let's look at the file. Open ~/.bashrc, and at the end of the file create an alias, __weather__, that maps to the following command:

    curl wttr.in/Houghton+mi

Aside from aliases, we also can set convenient variables here for our shell. To do so, we define the variable, then use `export` to be able to access a variable outside of the script it was defined in.

Environment Variables typically are in all caps.
Add the following line to your .bashrc to see this in action!

    export DATA1201_LABS="~/data1201/labs"


1. Take a screenshot of your .bashrc file, and save it as "bashrc.jpg" or "bashrc.png" im the lab9 folder.
2. Then, refresh your bash environment by using  `source ~/.bashrc`.
3. Run the command, `weather`, and take a screenshot. Save this in the lab9 folder as "weather.jpg" or "weather.png".
4. Next, change directories to your home directory, and print where you are using `pwd`
5. Finally, run the following three commands in the following order and see what they print out:
    1. `echo $DATA1201_LABS`
    2. `cd $DATA1201_LABS`
    3. `pwd`
6. Take a screenshot of your terminal, and save it as "environmentvar.png" or environmentvar.jpg"

## Step 3) Getting Input!
You should now be able to run `cd $DATA1201_LABS/lab9` to return to our lab folder for this lab now.

Inside of this folder, create a script called __populate.sh__, and give it execute permissions.

1. Inside of populate.sh, add the following lines:
```
#!/bin/bash
echo "First Echo: $@"
echo "Second Echo: $#"
echo "Third Echo: $0"
echo "Fourth Echo: $1"
```
2. Run `./populate.sh first second third fourth` and make note of the output
    1. in the file populate.sh, write a comment above each echo, explaining what each "$" means.

3. Make a for-each loop that loops over every argument provided to the file, with a loop that echoes "ARG: " followed by each argmuent. This loop should happen in the script after the initial several prints from part 1.
The output of the loop portion of the file will look like what is below:

> ARG: first
>
> ARG: second
>
> ARG: third
>
> ARG: fourth

## Step 4) Adding the lab9 directory to your git repository. 

1. In the lab9 folder, make it a git repository with `git init`

2. Commit all of the files in the directory!

3. Then, get the URL for your own repository on git, it should look something like
`git remote add "origin" git@github.com:YOUR_USERNAME/data1201.git`
Make sure you use the proper origin!

4. Then, update your local repository's knowledge of remote branches using `git fetch`

5. Next, set your local branch to point to the remote branch. Assuming both are named `main`, then `git branch --set-upstream-to=origin/main main`

6. Finally, pull from your repository using `git pull --allow-unrelated-histories` to handle merge conflicts.
    1. The `allow-unrelated-histories` flag ignores differences in commit history!  
    2. If you have errors, run `git config pull.rebase false` and then re-pull

Handle the conflicts, then push your changes to the remote repository!


# Post-Lab Assignment

## Step 1)

### Decisions: If
The `if` statement gates certain commands to only run when the condition it checks is true.

We can do an else-if chain using `elif` as else-if, and `else`.
Instead of using curly brackets { }, code is encompassed between `then` and `fi`.
    
    if [ cond1 ]; then
        # Code to be executed if condition1 is true
    elif [ cond2 ]; then
        # Code to be executed if condition2 is true
    else
        # Code to be executed if none of the conditions are true
    fi
    
Alternatively, we may only have a conditional on it's own:

    # This checks if a file does not exist!
    if [ ! -f $example_file ]; then
        echo "File does not exist!"
        exit
    fi

### Decisions: While
The `while` statement gates certain commands to continue running as long as a condition holds true.
The condition is checked at the start of each loop iteration.

Notice the scope is encompassed within `do` and `done`!

    while [ condition ]; do
        # statements
    done  
    
### Types of comparisons
There are many types of comparisons that are in bash. Since many times we are performing manipulation on files and strings, it has tools for comparing things such as files, strings, and integers.

A cheat sheet of comparison types in bash are located [here](https://kapeli.com/cheat_sheets/Bash_Test_Operators.docset/Contents/Resources/Documents/index). 

### Checking files
1. Inside of `$DATA1201_LABS/lab9`, make a script called __check.sh__.
2. Give execution permission to __check.sh__.
3. Have it take an argument.
    1. If the file does not have any arguments, print out "Provide a file to check"
    2. Then, run `exit 1` to close the file with an error code of 1.
4. If the file exists, print out the contents using `cat`
5. Otherwise, print out, `File does not exist!`.

Test the program with no arguments, with a file that exists, and with a file that does not exist. (Remember that files in another directory may require you to provide the file path).


