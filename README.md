# Final Report

## Objectives

The objectives of this project are as follows:

1. Develop a Linux kernel module to modify system call behavior.
2. Implement functionality to hide files and directories with a specific prefix.
3. Block certain system calls such as reboot and shutdown.
4. Explore the concepts of hooking and modifying system call table entries.

## Project Details

The project involves the development of a Linux kernel module that modifies system call behavior. The module hooks into various system calls and alters their functionality according to the project requirements. The key details of the project are as follows:

- The module is implemented using the Linux kernel module programming framework.
- The module utilizes the Linux kernel headers and libraries to access system call related data structures and functions.
- The module defines and uses several function pointers to store the original addresses of system calls that will be modified.
- The module modifies the behavior of the following system calls:
  - `rmdir`: Overrides the original system call to hide the directory being removed.
  - `mkdir`: Overrides the original system call to hide the created directory.
  - `getdents`: Overrides the original system call to hide files and directories with a specific prefix.
  - `reboot`: Optionally blocks the reboot system call based on a configuration flag.
  - `shutdown`: Optionally blocks the shutdown system call based on a configuration flag.
- The module dynamically looks up the addresses of the system calls using the `kallsyms_lookup_name` function.
- The module utilizes inline assembly code to modify the Control Register 0 (CR0) to enable or disable write protection on the kernel memory pages.
- The module hooks into the system call table to redirect the system calls to the custom implementations defined in the module.

## Results

The results of the project can be analyzed and compared through various means, including graphical representation. However, the provided code does not contain any specific code for collecting or presenting data for comparison. Therefore, no specific graphs or comparison results can be provided based on the given code.

## Conclusion

In conclusion, this project aimed to develop a Linux kernel module that modifies system call behavior to achieve certain objectives. The module successfully implements functionality to hide files and directories with a specific prefix, as well as block certain system calls such as reboot and shutdown. It demonstrates the concept of hooking and modifying system call table entries to customize the behavior of the Linux kernel.

However, the provided code lacks comprehensive documentation and analysis of the results. In order to draw more meaningful conclusions and provide a thorough final report, it would be beneficial to conduct further experimentation, collect data, and analyze the impact of the implemented modifications on system behavior and performance.
