<!-- alias include -->

# Including headers
## What is [`#include`](https://en.cppreference.com/w/cpp/preprocessor/include)?
`#include` includes a header file into the current file at the line immediately after the directive. This is practically a copy paste done by the preprocessor.

## Include paths
`#include <...>` looks up the "include paths" that are specified by the system and compiler. You can add paths to this by:<br>
Passing `-I "some/directory/` on gcc/clang, `/I "some/directory/` on MSVC.<br>
Adding `target_include_directories(targetname PRIVATE some/directory/)` in CMake

`#include "..."` looks up the directory relative to the source file it's in. If it didn't find the header file that way, it looks up the include paths as a fallback.

## Misconceptions:
Header files have the minimal information necessary for the compiler at compile time.<br>
A header simply contains the declarations of symbols, stating that the given thing exists, but it doesn't give a definition.

This means, that you can't "include a library" just by including its header files.

## Don't -s

Do not include source(`.c, .cpp`) files.
They contain definitions, which, according to [ODR](https://en.cppreference.com/w/cpp/language/definition) should only appear once. Including them would make a copy of all the definitions in them.
