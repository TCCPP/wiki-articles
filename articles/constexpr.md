<!-- alias constexpr -->

# `constexpr` in C and C++

The `constexpr` keyword gives the compiler permission to evaluate a variable or function at compile time when needed in
a constant-expression context. Such contexts include:
- Template parameters
- `case` labels
- Array sizes

## Is `constexpr` for optimization?

The compiler can do constant evaluation and constant-propagation as part of optimization without `constexpr`. The
primary purpose of `constexpr` really is just giving the compiler permission to perform such evaluation in certain
contexts where it's absolutely required to have a compile-time value. Outside of these contexts, `constexpr` *does not*
mandate that the compiler must perform constant evaluation, even if it is possible, however, it can make an impact on
the code generated by some compilers. Additionally, `constexpr` variables are required to have compile-time evaluable
initializers.

## `if constexpr`

As with many keywords in C++, `constexpr` has multiple meanings. In an `if constexpr` statement it can be used to
conditionally discard code at compile time. This is useful in templates, when depending on properties of a type one
ranch might not be able to be compiled.