# How to Add a library reference to your program without the use of various package managers like
# nuget and stuff . 
# For the mono runtime , language = csharp . 

1. you have the following files in this filesystem : 
	> /mainprog.cs		[contains the main method of the program.]
	<br>
	> /libs/math.cs		[this is the uncompiled library code.]

2.
 In mono , we have various compilation targets , including library and executable.
 To compile code to a library target in mono we use the target:<TYPE> FLAG during compilation in the cli
 [command line interface] and compile the program code . 

 NOTE that the library can contain a Main method , which can allow it to be executed. 

 compile /libs/maths.cs to library [dynamic library]
		mcs math.cs -target:library
 --> a dll file is obtained , provided there are no compile time errors in the code . 

3. 
 To use the library , you must import the namespace of the library code into your main program , 
 and you should ensure that the library dll lies in the same directory of your compiled program 
 executable. 

4. 
 Finally , compile the main program code into (exe), and reference the libraries that you used ,
 using the -reference:<dllname> FLAG. 

		mcs mainprog.cs -reference:math.dll
 // compilation is done successfully , unless there are runtime errors in the program , or the
	referenced dll is not found in the same path as you placed in the compiling option. 

5. 
 run the program using mono . 
	mono mainprog.exe
 --> the program runs successfully , unless the library file is not found in the same directory as the
	main compiled exe. 


===================================== Y O U R	W E L C O M E ================================= 

THANKS FOR LISTENING TO MY TED TALK.
