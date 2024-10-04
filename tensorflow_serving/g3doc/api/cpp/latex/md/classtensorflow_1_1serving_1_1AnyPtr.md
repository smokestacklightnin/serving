::: {#classtensorflow_1_1serving_1_1AnyPtr}
:::

[\[classtensorflow\_1\_1serving\_1\_1AnyPtr\]]{#classtensorflow_1_1serving_1_1AnyPtr
label="classtensorflow_1_1serving_1_1AnyPtr"}

\#include $<$any\_ptr.h$>$

[\[classtensorflow\_1\_1serving\_1\_1AnyPtr\_a0250c65b7f2f4747e8050620f498b51c\]]{#classtensorflow_1_1serving_1_1AnyPtr_a0250c65b7f2f4747e8050620f498b51c
label="classtensorflow_1_1serving_1_1AnyPtr_a0250c65b7f2f4747e8050620f498b51c"}
[AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr_a0250c65b7f2f4747e8050620f498b51c)
()

*[AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr) is void and null by
default.*

[\[classtensorflow\_1\_1serving\_1\_1AnyPtr\_a9e716e1e923c2094e4e88e83d9800595\]]{#classtensorflow_1_1serving_1_1AnyPtr_a9e716e1e923c2094e4e88e83d9800595
label="classtensorflow_1_1serving_1_1AnyPtr_a9e716e1e923c2094e4e88e83d9800595"}
[AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr_a9e716e1e923c2094e4e88e83d9800595)
(std::nullptr\_t)

*Implicit construction from nullptr.*

[\[classtensorflow\_1\_1serving\_1\_1AnyPtr\_a90f5c7399a7ae6d4847d9f86669fcab7\]]{#classtensorflow_1_1serving_1_1AnyPtr_a90f5c7399a7ae6d4847d9f86669fcab7
label="classtensorflow_1_1serving_1_1AnyPtr_a90f5c7399a7ae6d4847d9f86669fcab7"}
template$<$typename T $>$ \
[AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr_a90f5c7399a7ae6d4847d9f86669fcab7)
(T $\ast$ptr)

*Construct from a pointer to any type.*

[\[classtensorflow\_1\_1serving\_1\_1AnyPtr\_a357cf7dcf137a8064c393b486509d218\]]{#classtensorflow_1_1serving_1_1AnyPtr_a357cf7dcf137a8064c393b486509d218
label="classtensorflow_1_1serving_1_1AnyPtr_a357cf7dcf137a8064c393b486509d218"}
template$<$typename T $>$ \
T $\ast$
[get](#classtensorflow_1_1serving_1_1AnyPtr_a357cf7dcf137a8064c393b486509d218)
() const

*Accessor for the underlying pointer if it is of type T, otherwise
null.*

A (sort of) type-safe void$\ast$. Appears as null if a caller attempts
to use it as the wrong type.

Example use:

// A function that returns an
[AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr):
[AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr) StringOrInt() { if
(use\_string) { return AnyPtr(&some\_string); } else { return
AnyPtr(&some\_int); } }

// Use an [AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr) at the correct
type: [AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr) ptr =
StringOrInt(); if (ptr.get$<$int$>$() != nullptr) {
DoSomethingWithInt($\ast$ptr.[get$<$int$>$()](#classtensorflow_1_1serving_1_1AnyPtr_a357cf7dcf137a8064c393b486509d218));
} else if (ptr.get$<$string$>$() != nullptr) {
DoSomethingWithString($\ast$ptr.[get$<$string$>$()](#classtensorflow_1_1serving_1_1AnyPtr_a357cf7dcf137a8064c393b486509d218));
} else { // Handle error. }

Typical best practice for this class is to use it when two disjoint
pieces of code must agree on type, but intermediate code is type
agnostic. Large chains of conditionals that handle a multitude of types
is discouraged as an anti-pattern.

Note that this will appear null even if T is somewhere on the underlying
types inheritance hierarchy, if you must use the object at some other
type you must do so explicitly when constructing an
[AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr), like so:

SomeObject object; [AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr)
any\_ptr(static\_cast$<$SomeInterface$\ast$$>$(&object));
SomeInterface$\ast$ interface = any\_ptr.get$<$SomeInterface$>$();

This class is a value type; It can be copied or assigned. It performs no
internal allocations and should be relatively cheap to copy or return by
value.

The documentation for this class was generated from the following file:

tensorflow\_serving/util/any\_ptr.h
