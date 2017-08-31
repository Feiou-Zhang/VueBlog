title: Post
------------------------------------
<!-- en-US:+ -->

### Common methods

>charAt(int index)

>codePointAt(int index)

>substring(int start, int end) the start index will be included and the end index will be not. same as the delete method from the StringBuilder class.

>substring(int start)

StringBuilder:

Most of the methods will return a StringBuilder type:

append(char/char[]/String/StringBuilder)

delete(int start, int end), deleteCharAt(int index),

insert(int index, char c/String str)

replace(int start, int end, String str)

reverse

However, the setCharAt(int index) will return a void type.

String:

 *Important*

compareTo(String str): this could be a little bit tricky, it first compares the unique code for each character until the first difference no matter which one gets the longer length. If all the characters are the same, it will compare the length and return the difference.

There is a contains method but need CharSequence type of parameter.

the concat(String str) will be as same as +, but will not be less efficient than the append method of the StringBuilder

startsWith(String str), endsWith(String str), be careful the 's' and these two methods only take String type of parameter, will not take char or char[].

the indexOf(int ch, char ch, String str) will do the String Matching for you, but it is using the brute force algorithm. 

the replace(char old, char new) will be different with the replace of the StringBuilder Class

there is ONLY one static method in the String class which is valueOf()





