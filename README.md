# Brute Force Style Guide

## Disclaimer
The point of a style guide is to make code easier to read and expand, not make it harder.
If you need to violate the style guide to write code, then please do so.

## File Structure
Each file should only contain one class.
All source files should use PascalCase, end with .cpp, and be in the src directory
All header files should also use PascalCase, end with .h and be in the include directory
There should be no other types of files in either directory.

## Formatting
Try to keep all lines to 79 characters or less.

Opening curly brackets should be below the line of their corresponding statement
like this:
```
int main 
{
    return 0;
}
```
not like this:
```
if ( foo == bar ) {
    return 0;
}
```

For struct and enum types, likewise put the braces on a newline, unless the whole contents fits on one line: 
```
struct foo
{
  int a, b;
}
// Or,

struct foo { int a, b; }
```
It is also ideal to put spaces before and after mathematical operators (+ - = / * etc...) as well as parentheses.

For indentation, spaces should be used instead of tabs.
If your editor has the capability to, enable GNU style indentation in settings.

## Naming

### Cases
All classes and files should use PascalCase.
PascalCase is a capital letter at the start of each word, including the first letter.

Mutable variables, methods and functions should use snake_case, where all letters are lowercase and separated with underscores.

Constant variables (including motors) should use SCREAMING_SNAKE_CASE, with all letters capitalized and words separated by underscores

Namespaces should use SCREAMING_SNAKE_CASE as well.

Hungarian notation should not be used as it makes variables less legible.
However, for mutable variables defined in a header file (such as joystick), their names should start with an `m_`
an example would be `m_variable_defined_in_header_file` note the snake_case

## Comments

Each class and method should have a documentation comment explaining what it does and why, unless the code is self explanitory.
Documentation comments should go directly below the opening bracket of the method or the very start of a class header.
```
/**
* This is an example documentation comment
* It is also multiline
**/
```
`/** Single line documentation comment **/`

A comment is NOT an alternative for deleting code. Delete code, don't comment it out.
No comment is better than a wrong comment.
Link your sources. For example, if you copy code from stack overflow, throw in a link to the post.
No inline comments. Put each comment on it's own line as a full sentence. Other people will read them, not just you.
Comments tell you why certain code was written, code tells you how it works.

## Misc.

For constants, use `constexpr type NAME = value;`, instead of `#DEFINE NAME value` or `static const type NAME = value;`
Avoid using "magic numbers" (such as a pre-determined RPM or a known distance) directly in functions, instead, use a constant variable.
All constants should be in one file, seperated by namespace.

Pointers should be declared with the askerisk before the name, not the type. An example of this would be:
`int *ptr; //do this`
As opposed to:
`int* ptr; //not this`

---
This guide was based off the [GNU C style guide](https://www.gnu.org/prep/standards/html_node/Writing-C.html)
