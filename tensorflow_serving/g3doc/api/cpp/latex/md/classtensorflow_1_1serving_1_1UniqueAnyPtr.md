::: {#classtensorflow_1_1serving_1_1UniqueAnyPtr}
:::

[\[classtensorflow\_1\_1serving\_1\_1UniqueAnyPtr\]]{#classtensorflow_1_1serving_1_1UniqueAnyPtr
label="classtensorflow_1_1serving_1_1UniqueAnyPtr"}

\#include $<$any\_ptr.h$>$

[\[classtensorflow\_1\_1serving\_1\_1UniqueAnyPtr\_a2289c5328e883bc22bd79fc7b7262244\]]{#classtensorflow_1_1serving_1_1UniqueAnyPtr_a2289c5328e883bc22bd79fc7b7262244
label="classtensorflow_1_1serving_1_1UniqueAnyPtr_a2289c5328e883bc22bd79fc7b7262244"}
[UniqueAnyPtr](#classtensorflow_1_1serving_1_1UniqueAnyPtr_a2289c5328e883bc22bd79fc7b7262244)
()=default

*[UniqueAnyPtr](#classtensorflow_1_1serving_1_1UniqueAnyPtr) is void and
null by default.*

[\[classtensorflow\_1\_1serving\_1\_1UniqueAnyPtr\_a828c00154987e28e4909dfadf5a9cad4\]]{#classtensorflow_1_1serving_1_1UniqueAnyPtr_a828c00154987e28e4909dfadf5a9cad4
label="classtensorflow_1_1serving_1_1UniqueAnyPtr_a828c00154987e28e4909dfadf5a9cad4"}
**UniqueAnyPtr** (std::nullptr\_t)

[\[classtensorflow\_1\_1serving\_1\_1UniqueAnyPtr\_ae33840e17d58e1e45a77306e8c0312a5\]]{#classtensorflow_1_1serving_1_1UniqueAnyPtr_ae33840e17d58e1e45a77306e8c0312a5
label="classtensorflow_1_1serving_1_1UniqueAnyPtr_ae33840e17d58e1e45a77306e8c0312a5"}
template$<$typename T $>$ \
[UniqueAnyPtr](#classtensorflow_1_1serving_1_1UniqueAnyPtr_ae33840e17d58e1e45a77306e8c0312a5)
(std::unique\_ptr$<$ T $>$ ptr)

*Construct from a unique pointer to any type.*

[\[classtensorflow\_1\_1serving\_1\_1UniqueAnyPtr\_a247ff3d59e6df37d7c98adc9680f8fb2\]]{#classtensorflow_1_1serving_1_1UniqueAnyPtr_a247ff3d59e6df37d7c98adc9680f8fb2
label="classtensorflow_1_1serving_1_1UniqueAnyPtr_a247ff3d59e6df37d7c98adc9680f8fb2"}
**UniqueAnyPtr** (const
[UniqueAnyPtr](#classtensorflow_1_1serving_1_1UniqueAnyPtr)
&other)=delete

[\[classtensorflow\_1\_1serving\_1\_1UniqueAnyPtr\_a88bba0bf01d730b9b367179310b7953e\]]{#classtensorflow_1_1serving_1_1UniqueAnyPtr_a88bba0bf01d730b9b367179310b7953e
label="classtensorflow_1_1serving_1_1UniqueAnyPtr_a88bba0bf01d730b9b367179310b7953e"}
[UniqueAnyPtr](#classtensorflow_1_1serving_1_1UniqueAnyPtr) &
**operator=** (const
[UniqueAnyPtr](#classtensorflow_1_1serving_1_1UniqueAnyPtr)
&other)=delete

[\[classtensorflow\_1\_1serving\_1\_1UniqueAnyPtr\_a9cd8acbcc8592aa2b8975475f4f4f4ea\]]{#classtensorflow_1_1serving_1_1UniqueAnyPtr_a9cd8acbcc8592aa2b8975475f4f4f4ea
label="classtensorflow_1_1serving_1_1UniqueAnyPtr_a9cd8acbcc8592aa2b8975475f4f4f4ea"}
**UniqueAnyPtr**
([UniqueAnyPtr](#classtensorflow_1_1serving_1_1UniqueAnyPtr) &&other)

[\[classtensorflow\_1\_1serving\_1\_1UniqueAnyPtr\_aa8e547b42286ffb54b9e1ac351b3bce1\]]{#classtensorflow_1_1serving_1_1UniqueAnyPtr_aa8e547b42286ffb54b9e1ac351b3bce1
label="classtensorflow_1_1serving_1_1UniqueAnyPtr_aa8e547b42286ffb54b9e1ac351b3bce1"}
[UniqueAnyPtr](#classtensorflow_1_1serving_1_1UniqueAnyPtr) &
**operator=**
([UniqueAnyPtr](#classtensorflow_1_1serving_1_1UniqueAnyPtr) &&other)

[\[classtensorflow\_1\_1serving\_1\_1UniqueAnyPtr\_acb57a78f3357bd37e85a25ca707d692b\]]{#classtensorflow_1_1serving_1_1UniqueAnyPtr_acb57a78f3357bd37e85a25ca707d692b
label="classtensorflow_1_1serving_1_1UniqueAnyPtr_acb57a78f3357bd37e85a25ca707d692b"}
template$<$typename T $>$ \
T $\ast$
[get](#classtensorflow_1_1serving_1_1UniqueAnyPtr_acb57a78f3357bd37e85a25ca707d692b)
() const

*Accessor for the underlying pointer if it is of type T, otherwise
null.*

[\[classtensorflow\_1\_1serving\_1\_1UniqueAnyPtr\_a5b06edf7f9381bbae5a1fbc903d0e2f0\]]{#classtensorflow_1_1serving_1_1UniqueAnyPtr_a5b06edf7f9381bbae5a1fbc903d0e2f0
label="classtensorflow_1_1serving_1_1UniqueAnyPtr_a5b06edf7f9381bbae5a1fbc903d0e2f0"}
const [AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr) &
[as\_any\_ptr](#classtensorflow_1_1serving_1_1UniqueAnyPtr_a5b06edf7f9381bbae5a1fbc903d0e2f0)
() const

*Accessor for the underlying pointer as an
[AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr).*

[\[classtensorflow\_1\_1serving\_1\_1UniqueAnyPtr\_ab93984c044a1c82415f4304b269b7f54\]]{#classtensorflow_1_1serving_1_1UniqueAnyPtr_ab93984c044a1c82415f4304b269b7f54
label="classtensorflow_1_1serving_1_1UniqueAnyPtr_ab93984c044a1c82415f4304b269b7f54"}
void **swap**
([UniqueAnyPtr](#classtensorflow_1_1serving_1_1UniqueAnyPtr) &other)

Like [AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr), but owns the
pointed-to object (calls delete upon destruction). This class is
move-only, like std::unique\_ptr.

The documentation for this class was generated from the following file:

tensorflow\_serving/util/any\_ptr.h
