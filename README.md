# Custom-Python-Executable
Define your own python executable extension and convert your simple python code to an executable application very easily. Make sure you have python.exe on your computer.

**The following steps need to be executed in the cmd with Administrator privileges**

### Step 1:

> ```
>   ASSOC .myexe=PythonScriptExecutable
> ```

*ASSOC is a command that displays the program and/or functionality ASSOCiated with a specific file type.* 
* This associates your own extension to a future path to be an executable (both chosen by you). Here for demo purposes I let:

-   `.myexe`  be my extension, and
-   `PythonScriptExecutable`  be used to set a  `python.exe`  in the next step

### Step 2:

> ```
>   FTYPE .myexe=PythonScriptExecutable=path/to/your/python.exe %1 %*
> ```

*FTYPE is used to display or change the link between a file type and an executable program.* 
* The `%1 %*` is a modifier to match the arguments we are passing to the cmd prompt, please do not miss that out. 
* In case you aren't sure about your python installation location, run the following code in a .py file and it will give you your python's location.
    
    > import sys
    >    print(sys.prefix)
    
Suppose it returns `"C://Programs//SomeFolder//python.exe"`  then simply change the  `//`  with  `\` i.e.  `C:\Programs\SomeFolder\python.exe`  and use this path in step up replacing it with "path/to/your/python.exe". This needs to be done for Windows users, also since python interpreter considers `/` as a special character and thus uses `//` to escape it.

### Step 3

> ```
>   set PATHEXT=%PATHEXT%;.myexec
> ```

And voila! You just defined .myexec as your custom python executable. Now all you need to do is write some python code and save it as filename.myexec
Then simply clicking on the file it will run automatically like any other executable. You can run it from the command prompt and also give parameters.
