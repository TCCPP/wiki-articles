# What Is an Ill-Formed Program?

An [ill-formed][ill-formed] program
(as opposed to a [well-formed][well-formed] program)
is "not valid standard C++".
Compilers are required to raise a
[diagnostic message][diagnostic message] (warning or error)
when given an ill-formed program.

<!-- inline -->
## Ill-Formed Example A
```cpp
{#/;
```
Compilers should raise a syntax error here.

<!-- inline -->
## Ill-Formed Example B
```cpp
int a[0];
```
Zero-size arrays
[are not allowed](https://eel.is/c++draft/dcl.array#1),
but some compilers support them as an [extension][extension].

## Ill-Formed, No Diagnostic Required (IFNDR)
In some cases, the program is ill-formed,
but diagnostics are not required
(usually because it would take "heroic" compiler effort).
For example, having a template which can never be instantiated makes a
program [IFNDR][IFNDR].


[diagnostic message]: https://eel.is/c++draft/defns.diagnostic
[extension]: https://eel.is/c++draft/intro.compliance#general-9
[ill-formed]: https://eel.is/c++draft/defns.ill.formed
[well-formed]: https://eel.is/c++draft/defns.well.formed
[IFNDR]: https://eel.is/c++draft/intro.compliance#general-2.2
