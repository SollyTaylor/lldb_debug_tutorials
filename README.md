# lldb_debug_tutorials
some lldb debugging tutorials and conventional usages

typical procedures:

1. fire the lldb in command line
      
  ```
  $ lldb
  ```
      
2. load the binary file of executable (e.g. `program_debug`)
      
  ```
  (lldb) file program_debug
  ```

3. launch process with demanded program arguments
  
  ```
  (lldb) process launch -- <arguments feed to the program_debug>
  ```

4. after some running, the code would encounter a crash or exception from somewhere, at this time, add breakpoint at the crashing line of code and launch process again
  
  ```
  (lldb) breakpoint set --file <file_to_break>.cpp --line <line_number>
  (lldb) process launch -- <arguments feed to the program_debug>
  ```

5. the program would break at the breakpoint, it's the right time to checkout the stack data for the crashing details, using bt command (short for traceback) to print the stack data
  
  ```
  (lldb) bt
  ```

related useful links:

1. [GDB and LLDB debugging command examples](https://developer.apple.com/library/mac/documentation/IDEs/Conceptual/gdb_to_lldb_transition_guide/document/lldb-command-examples.html#//apple_ref/doc/uid/TP40012917-CH3-SW1)
2. [Using LLDB as a standalone debugger](https://developer.apple.com/library/mac/documentation/IDEs/Conceptual/gdb_to_lldb_transition_guide/document/lldb-terminal-workflow-tutorial.html#//apple_ref/doc/uid/TP40012917-CH4-SW1) which means the user need not extra IDE assistance.
