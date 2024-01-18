   # Setup Debugging under VS Code on MacOS
   
   The following describes how to setup VS Code debugging to support passing command line arguments and 
   redirecting input to the debugged program.

   Place the code below in the **.vscode/launch.json** file:

   ***"args"*** are passe to the debug program as command line parameters.
   ***"input.txt"*** is the source of redirected stdin.  Change as needed.

   ``` json
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    // See here for variable names: https://code.visualstudio.com/docs/editor/variables-reference
    // See here for post describing redirecting input: 
    //     https://vincepergolizzi.com/programming/2018/04/03/vscode-lldb-debugging-stdin.html
    // "args" are passed to debug program as command line parameters.
    // "input.txt" is the source of redirected stdin.  Change as needed.
    {
    "configurations": [
        {
            "name": "C/C++: clang++ build and debug active file",
            "type": "cppdbg",
            "request": "launch",
            "program": "${fileDirname}/${fileBasenameNoExtension}",
            "args": [
                "another",
                "try"
            ],
            "stopAtEntry": false,
            "cwd": "${fileDirname}",
            "environment": [],
            "externalConsole": false,
            "MIMode": "lldb",
            "preLaunchTask": "C/C++: clang++ build active file",
            "setupCommands": [
                {
                    "text": "settings set target.input-path input.txt"
                }
            ]
        }
    ],
    "version": "2.0.0"
    }
   ```
