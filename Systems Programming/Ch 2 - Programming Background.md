## Program Development Steps
1. Create source files
```
// t1.c
int g = 100; //initialized global variable
int h; //uninitialized global variable
static int s; // static global variable

main(int argc, char* argv[])
{
	int a=1; int b; //automatic local variables
	static int c = 3; //static local variable
	b = 2;
	c = mysum(a,b); //call mysum(), passing a,b
	printf("sum=%d\n",c); //call printf()
}
```

```
// t2.c
extern int g; //global extern variable
int mysum(int x, int y){
	return x + y + g;
}
```
### Variables in C
- **Global**: ( Defined outside any function)
	- **Non-static globals**: visible to all the files of the same program.
	- **Static Globals**: Visible only to the function they in which they are defined.
	-  **Initialized** global variables are assigned values at compile time whereas **unitialized** global variables are cleared to 0 when execution starts.
-  **Local**: (Defined inside a function, by default are *automatic* variables and visible only to that function in which they are defined)
	-  **Register**: compiler tries to allocated them to CPU registers. 
	-  **automatic**: come into existence when the function is entered and logically disappear when the function exits. They cannot be initialized at compile time.
	-  **static**: permanent and unique.
-  **Volatile** : used as memory-mapped I/O or global variables that are accessed by interrupt handlers or multiple execution threads.
2. Convert the source files to a binary executable.
	- `gcc t1.c t2.c`
3. *Gcc* is a program that consists of three major steps.
	- **Step 1**: Convert .c ie source files to .s files ie assembly code.
	- **Step 2**: Convert assembly code to object code or machine code. ( .o files)
	- Each .o files consists of 
		- **header** : containing sizes of CODE,DATA and BSS sections
		- **CODE** section containing machine instructions.
		- **DATA** section containing initialized globals and initialized static local variables.
		- **BSS** section uninitialized globals and uninitialized static local variables.
		- **relocation** information for pointers in CODE and offsets in DATA and BSS
		- a **symbol table** containing non-static globals, function names and their attributes. 
	- **Step 3**: LINKING: Combines all the .o files and the needed library files into a single binary executable file. Specifically it does the following:
		- Combine all CODE sections of the .o files into a single Code section. For C, the combined code section begins with **crt0.0** function which calls the main() function which is why there must be only one  main function in the entire program.
		- Combine all the DATA sections into a single data section that contains only initialzed globals and initialzed static local variables.
		- Combine all the BSS sections to a single BSS section.
		- Use the relocation information in the .o files to adjust pointers in the combined Code section and offsets in the combined Data and BSS sections.
		- Use the symbol table to resolve cross references among the individual .o files. If all the cross references can be resolved successfully, the linker writes the resulting combined file as a.out, which is the binary executable.

### Static vs. Dynamic Linking
These are two ways of creating a binary executable. 
- In static linking, all the required library code is present in the a.out file itself.
- In Dynamic linking, calls to library functions are stored as directives in a.out and whenever a.out is executed the OS loads both the Dynaminc Link Library needed and the a.out file in memory for it to execute. These libraries are also called shared libraries (with .so extensions)
- Main advantages of dynamic link libraries (DLL) are that size of a.out is reduced and modifying library functions doesn't require re-compilation of the source files.

### Executable File Format
Most C compilers and linker can products executables in different file formats, they are: 
- **Flat Binary Executable** : Consists of only the executable code and initialized data, intended to be loaded entirely into memory to be executed directly. eg: Bootable OS images.
- **a.out executable file**: Traditional a.out file consists of a header, followed by code, data and bss sections.
- **ELF executable file**: In linux, the default executable files are ELF(Executable and Linking Format) Files which are better suited to dynamic linking.


### Contents of a.out file

	




