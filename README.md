Download Link: https://assignmentchef.com/product/solved-cs135-project-9
<br>
<u>Project [9]: Command Line arguments, Dynamic Memory</u> <u>allocation, and Strings</u>




<strong>Project Goals </strong>

The goal of this project is to:

<ol>

 <li>Get students familiar with command line arguments</li>

 <li>Get students familiar with dynamic memory allocation</li>

 <li>Get students familiar with arrays of pointers</li>

</ol>




<strong><u>Important Notes:</u> </strong>1. <strong>Formatting: </strong>Make sure that you follow the precise recommendations for the output content and formatting: for example, do not change the text in the first problem from “Please enter a string of maximum 30 characters: ” to “Enter string:”. Your assignment will be auto-graded and any changes in formatting will result in a loss in the grade.

<ol start="2">

 <li><strong>Comments:</strong> Header comments are required on all files, for each function, and recommended throughout the rest of the program. Points will be deducted if no header/function are included.</li>

 <li><strong>Restriction: </strong>The use of goto statements anywhere within this program is prohibited. Points will be deducted if gotois used.</li>

</ol>




<strong>Problem 1 </strong>

Write a program that asks the user to enter two strings (with a maximum length of 30) and then performs one of two possible operations provided as command line arguments to the program. The possible command line options and the associated operations are as follows:

<ul>

 <li>Option “-i” Operation: If given this option, the program should create a new string that is built by interspersing the two strings. The program will alternatively place one character at a time from each string into the new string. When one of the strings is exhausted, the program should copy the remaining characters from that string into the new string. This functionality should be implemented in a function called intersperse, which takes as parameters the two strings and returns a pointer to the newly created string. Your function should use dynamic memory allocation to generate the new string.</li>

</ul>




For example, if string 1 is “abcde” and string 2 is “1234567”, the resulting string should be “a1b2c3d4e567”.




<ul>

 <li>Option “-w” Operation: If given this option, the program should create a new string that is built by concatenating the two given strings, in which there has been a ‘*’ character inserted in between every character in those strings. There should be a ‘*’ character between the two strings, but no such character at the end of string 2. This functionality should be implemented in a function called widen_stars, which takes as parameters the two strings and returns a pointer to the newly created string. Your function should use dynamic memory allocation to generate the new string.</li>

</ul>




For example, if string 1 is “abcde” and string 2 is “1234567”, the resulting string should be “a*b*c*d*e*1*2*3*4*5*6*7”.

Your program should function as follows (items underlined are to be entered by the user):

&gt; gcc combine_strings.c -o combine_strings

&gt; ./combine_strings -i

Please enter a string of maximum 30 characters: <u>abcde</u>

Please enter a string of maximum 30 characters: <u>1234567</u> The combined string is: a1b2c3d4e567

Or

&gt; gcc combine_strings.c -o combine_strings

&gt; ./combine_strings -w

Please enter a string of maximum 30 characters: <u>abcde</u>

Please enter a string of maximum 30 characters: <u>1234567</u> The combined string is: a*b*c*d*e*1*2*3*4*5*6*7 <strong>Notes: </strong>

<ul>

 <li>You may not include the string library, but you may use the strlength and strcomp functions from the last project</li>

 <li>Before terminating, your program needs to de-allocate the space allocated for the newly created strings</li>

</ul>




Save your program as combine_strings.c




<strong>Problem 2 </strong>

This program will build off the last project. You will write an interactive program for strings. The number of strings will be provided as a command line argument. The user will enter the length of the string they are about to enter and then the string itself. After the program has read in the specified number of strings it will print the strings out and then print a menu that will allow the user to either: find the length of any string they want, compare any two strings, copy any string into another, or copy any string into another.

At every iteration, your program should:

<ol>

 <li>Print out the strings by first printing “Your strings are:” and then the strings in the format specified below</li>

 <li>Print out a menu as follows:</li>

</ol>

Options:

<ul>

 <li>– Find string length</li>

 <li>– Compare strings</li>

 <li>– Copy strings</li>

 <li>– Concatenate strings</li>

 <li>– Quit</li>

</ul>

<h1><a name="_Toc14306"></a>Please enter your option:</h1>

Below is a description of what the program should do for each of the above options.  (items underlined are to be entered by the user):

<ol>

 <li>Find the length of any string. You will use the strlength function. For this option, the program should ask the user to enter the number of the string they want to find the length of, as follows:</li>

</ol>

<h1><a name="_Toc14307"></a>Enter a string number: <u>1</u></h1>

The length of string 1 is: 5




<ol start="2">

 <li>Compare any two strings. You will use the strcomp For this option, the program should ask the user to enter the numbers of two strings and then print out which string comes first, as follows:</li>

</ol>

Enter the number of the first string: <u>4</u>

Enter the number of the second string: <u>2</u>

String 2 comes before string 4 alphabetically.




If the strings selected by the user are the same string, your program should output: “The two strings are the same.”

<ol start="3">

 <li>Copy any two strings. You will use the strcopy For this option, the program should ask the user to enter the numbers of two strings and then copy the source string into the destination string, as follows:</li>

</ol>

Enter the number of the source string: <u>3</u>

Enter the number of the destination string: <u>6</u>




<ol start="4">

 <li>Concatenate any two strings. Your function will use the strconcat For this option, your program should ask the user to enter the numbers of two strings and then add the source string to the end of the destination string, as follows:</li>

</ol>

Enter the number of the source string: <u>3</u>

Enter the number of the destination string: <u>6</u>




<ol start="5">

 <li>Exit the program. Your program must free any memory that was allocated before exiting.</li>

</ol>




Your program must use the four functions written in the last project but modified as necessary:

<ol>

 <li>strlength: This function will take as a parameter a character pointer to a string. It will return the length of the string, not including the null terminator. This function is exactly the same as the last project.</li>

 <li>strcopy: This function should take as parameters two character pointers to two strings (a source string and a destination string). First, the function must reallocate enough memory to hold the source string in the destination string. Then it will copy the source string into the destination string, including the null terminator. It will then return a pointer to the beginning of the destination string.</li>

 <li>strconcat: This function should take as parameters two character pointers to two strings (a source string and a destination string). First, the function should reallocate enough memory to add the source string to the end of the destination string. Then it will add the source string to the end of the destination string. It will then return a pointer to the beginning of the destination string.</li>

 <li>strcomp: This function will take as parameters two character pointers to two strings (string 1 and string 2). The function then compares the two strings and if the string 1 comes first alphabetically it returns 1. If the string 2 comes first alphabetically then it returns -1. If the strings are the same then the function returns 0. The function should compare the two strings one character at a time and return the appropriate value as soon as a difference is noticed between the strings. This function is exactly the same as the last project.</li>

</ol>




The program should function as follows (items underlined are to be entered by the user):

&gt; gcc dynamic_strings.c -o dynamic_strings

&gt; ./dynamic_strings 5

Enter the length of string 1: <u>5</u> Please enter string 1: <u>first</u>

Enter the length of string 2: <u>6</u>

Please enter string 2: <u>second</u>

Enter the length of string 3: <u>5</u> Please enter string 3: <u>third</u>

Enter the length of string 4: <u>6</u>

Please enter string 4: <u>fourth</u>

Enter the length of string 5: <u>5</u> Please enter string 5: <u>fifth</u> Your strings are:

String number 1 – “first”

String number 2 – “second” String number 3 – “third”

String number 4 – “fourth” String number 5 – “fifth”

Options:

<ul>

 <li>– Find string length</li>

 <li>– Compare strings</li>

 <li>– Copy strings</li>

 <li>– Concatenate strings</li>

 <li>– Quit</li>

</ul>

<a href="#_Toc14306">Please enter your option:                                                                                                                                                               1 </a>

<a href="#_Toc14307">Enter a string number:                                                                                                                                                                    3 </a>

<a href="#_Toc14308">The length of string 3 is:                                                                                                                                                                  5 </a>




Your strings are:

String number 1 – “first”

String number 2 – “second” String number 3 – “third”

String number 4 – “fourth” String number 5 – “fifth”

Options:

<ul>

 <li>– Find string length</li>

 <li>– Compare strings</li>

 <li>– Copy strings</li>

 <li>– Concatenate strings</li>

 <li>– Quit</li>

</ul>

Please enter your option: <u>2</u>

Enter the number of the first string: <u>3</u>

Enter the number of the second string: <u>4</u>

String 4 comes before string 3 alphabetically.

Your strings are:

String number 1 – “first”

String number 2 – “second” String number 3 – “third”

String number 4 – “fourth” String number 5 – “fifth”

Options:

<ul>

 <li>– Find string length</li>

 <li>– Compare strings</li>

 <li>– Copy strings</li>

 <li>– Concatenate strings</li>

 <li>– Quit</li>

</ul>

Please enter your option: <u>3</u>

Enter the number of the source string: <u>2</u>

Enter the number of the destination string: <u>5</u>

Your strings are:

String number 1 – “first”

String number 2 – “second” String number 3 – “third”

String number 4 – “fourth”

String number 5 – “second”

Options:

<ul>

 <li>– Find string length</li>

 <li>– Compare strings</li>

 <li>– Copy strings</li>

 <li>– Concatenate strings</li>

 <li>– Quit</li>

</ul>

Please enter your option: <u>4</u>

Enter the number of the source string: <u>4</u>

Enter the number of the destination string: <u>1</u>

Your strings are:

String number 1 – “firstfourth”

String number 2 – “second” String number 3 – “third”

String number 4 – “fourth”

String number 5 – “second”

Options:

<ul>

 <li>– Find string length</li>

 <li>– Compare strings</li>

 <li>– Copy strings</li>

 <li>– Concatenate strings</li>

 <li>– Quit</li>

</ul>

Please enter your option: <u>5</u> <strong>Notes: </strong>

<ul>

 <li>If the user enters an invalid menu option, the program should print “Invalid Option.” then it should print the menu again and ask for a valid option, as follows:</li>

</ul>

Invalid Option.

Your strings are:

String number 1 – “first”

String number 2 – “second” String number 3 – “third”

String number 4 – “fourth” String number 5 – “fifth” Options:

<ul>

 <li>– Find string length</li>

 <li>– Compare strings</li>

 <li>– Copy strings</li>

 <li>– Concatenate strings</li>

 <li>– Quit</li>

</ul>

Please enter your option:

<ul>

 <li>You may <strong>NOT </strong>include the string library. Inclusion of the string library will result in a grade of zero for this project. Use the functions from project 7 and make any necessary changes.</li>

 <li>You can assume the user will enter the size of each string correctly.</li>

 <li>In the last project you used static memory allocation and assumed a max string size of 20 characters. This is no longer the case. You must dynamically allocate memory for all your strings and it is your responsibility to free the memory before the program ends.</li>

 <li>For this program, you must take the number of strings in as a command line argument. This number will be stored as a string not as an integer. To get the integer value of a string use the atoi(argv[1]) function from stdlib. This function takes as a parameter a string and gives the equivalent integer value.</li>

</ul>




Save your program as dynamic_strings.c

“Did you ever hear the tragedy of Darth Malloc The Wise? I thought not. It’s not a story Java would tell you. It’s a C legend. Malloc was a C function so powerful and so wise that it could use machine language to allocate memory itself. It had so much knowledge of machine code it could create dynamically sized arrays. Unfortunately, it taught free everything it knew and one day free deallocated all of its memory. Ironic. It could allocate memory for others, but not itself.”

Code Wars: Episode III – Revenge of the C


