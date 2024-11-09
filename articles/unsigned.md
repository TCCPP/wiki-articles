# Why Should You Avoid Unsigned Integers?

Unsigned integers should generally be avoided because they have
[modular arithmetic][mod] (wrap around),
leading to surprising results:

```cpp
my_vector[negative_int] = /* ... */; 
```
**Bug:**: `negative_int` is implicitly converted to a huge positive integer,
but `operator[]` thinks we cannot pass negatives.

```cpp
auto deficit = target_size - size();
if (deficit > 0) { add_amount(deficit); }
else             { remove_amount(deficit); }
```
**Bug:**: Subtraction wraps around, so `deficit`
is never negative.

```cpp
unsigned i = /* ... */;
if (i > -1) { /* ... */ }
```
**Bug:**: The if statement is never entered because `-1` is
converted to
[`UINT_MAX`](https://en.cppreference.com/w/c/types/limits).

<!-- inline -->
## Recommendation

Use unsigned integers only for bit manipulation or I/O tasks;
prefer signed integers otherwise,
and avoid mixing signed/unsinged above all else.

Compiler warnings can be used to detect the issues above
(e.g. [`-Wsign-conversion`](https://gcc.gnu.org/onlinedocs/gcc/Warning-Options.html#index-Wsign-conversion)),
but they detect countless harmless cases.

<!-- inline -->
## See Also

- [CppCoreGuidelines ES.106][guide] *Don’t try to avoid negative values by using unsigned*
- [Bjarne Stroustrup - P1428][p1428] *Subscripts and sizes should be signed*

[mod]: https://en.wikipedia.org/wiki/Modular_arithmetic
[guide]: http://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines#Res-nonnegative
[p1428]: https://www.open-std.org/jtc1/sc22/wg21/docs/papers/2019/p1428r0.pdf
