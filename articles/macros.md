# Why Should Preprocessor Macros Be Avoided?

Macros work by simply replacing text,
making them difficult to use and possibly unsafe.
Almost always, C++ offers better alternatives such as function templates.
Two common macro issues are shown below.

<!-- inline -->
## :one: Unsanitized macros

```cpp
#define A(cond) \
  if (!cond) return
if (y) A(z);
else break; // for A(z) ?!
```
The `if (!z)` within `A(z)` "steals" the
`else` statement so that it doesn't apply to `if (y)`.

<!-- inline -->
## :two: Multiple evaluations

```cpp
#define max(a, b) \
  (a > b ? a : b)
int x =
  max(read_int(file), 0);
```
If `read_int(file) > 0` is `true`,
`read_int(file)` is called a second time,
which is problematic if the file contains only one `int`.
