# Why can templates only be implemented in the header file?

The only portable way of using templates at the moment is to implement them in header files by using inline functions.

When instantiating a template, the compiler creates a new class/function with the given template argument.

The compiler needs to have access to the implementation of the class methods or the function to instantiate them with the template argument. If these implementations were not in the header, they wouldn't be accessible, and therefore the compiler wouldn't be able to instantiate the template.

## Alternative solution

Another solution is to keep the implementation separated, and explicitly instantiate all the template instances you'll need.

```cpp
//foo.hpp
//no method implementations
template <typename T> struct Foo { ... };
```

```cpp
//foo.cpp
//implementation of Foo's methods here...

//explicitly instantiate Foo<T> with the needed template arguments
//you will only be able to use Foo with T=int and T=float
template class Foo<int>;
template class Foo<float>;
```