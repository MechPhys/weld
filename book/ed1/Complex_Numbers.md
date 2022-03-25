---
title: "WELDBook Complex Numbers"
---

i{{\< /math \>}}, where {{\< math \>}}i^2 = -1{{\< /math \>}}, is what
keeps these two values orthogonal --- the first value {{\< math
\>}}a{{\< /math \>}} is along the real axis, and the second value {{\<
math \>}}b{{\< /math \>}} is along the imaginary axis. The complex
conjugate, {{\< math \>}}c^\*{{\< /math \>}}, is simply subtracting the
imaginary part instead of adding it (i.e., it represents a reflection
along the imaginary dimension). Multiplying {{\< math \>}}c c^\* {{\<
/math \>}} gives the squared magnitude of the vector, which is a single
real-valued scalar number. It is the (squared) length of the hypotenuse
of the vector.}}

We now introduce the symbol {{\< math \>}}\\phi{{\< /math \>}} (another
variant of the Greek symbol "phi", like {{\< math \>}}\\varphi{{\< /math
\>}}) to represent a complex-valued state variable:

-   {{\< math \>}} \\phi = a + i b {{\< /math \>}}



{{\< math \>}} = \\varphi_a + i \\varphi_b {{\< /math \>}}

So, {{\< math \>}}\\phi{{\< /math \>}} is composed of two separate
real-valued numbers, designated {{\< math \>}}a{{\< /math \>}} and {{\<
math \>}}b{{\< /math \>}} (or {{\< math \>}}\\varphi_a{{\< /math \>}}
and {{\< math \>}}\\varphi_b{{\< /math \>}}, to indicate that they are
scalar state variables). A complex number is really just a way of
representing two separate real valued numbers, aligned along orthogonal
dimensions, in an efficient and compact manner
(Figure\~\\ref{fig.complex_numbers}). It is essential to appreciate
that, despite the presence of the imaginary number {{\< math \>}}i{{\<
/math \>}} (where {{\< math \>}}i^2 = -1{{\< /math \>}} or {{\< math
\>}}i = \\sqrt{-1}{{\< /math \>}}), *all you ever really have is two
real-valued numbers*. There is nothing "imaginary" or mysterious or
spooky about the second number in a complex number: all the {{\< math
\>}}i{{\< /math \>}} does is keep these two values separate from each
other. In the end, we will deconstruct all of our complex numbers into
their real-valued components, and write purely real-valued expressions
that determine their update rules. These expressions will be more
complicated than the ones using complex numbers, but they are required
for actually implementing the equations on the computer, and they also
provide a more explicit and obvious indication of exactly what drives
each value.

Here's a few interesting facts about complex numbers:

-   To do algebra on them, you just have to remember to *keep the
    real-values sorted separately from the imaginary ones*, but
    otherwise treat them just like a pair of numbers:
    -   {{\< math \>}} y = a + ib {{\< /math \>}}
    -   {{\< math \>}} z = c + id {{\< /math \>}}
    -   {{\< math \>}} y + z = (a + c) + i(b + d) {{\< /math \>}}
    -   {{\< math \>}} y z = a c + i a d + i b c - b d {{\< /math \>}}



{{\< math \>}} = (ac - bd) + i (ad + bc) {{\< /math \>}}

Notice that this multiplication rule is the same as {{\< math \>}}(a +
b)(c + d) = ac + ad + bc + bd{{\< /math \>}}, where you just multiply
everything through, except that you end up with these {{\<
math \>}}i{{\< /math \>}} terms crossing over, and when you multiply
{{\< math \>}}ib{{\< /math \>}} and {{\< math \>}}id{{\< /math \>}}, you
end up with {{\< math \>}}i^2bd{{\< /math \>}}, at which point the {{\<
math \>}}i^2{{\< /math \>}} disappears into a {{\< math \>}}-1{{\<
/math \>}} (i.e., it crosses over from the imaginary world into the real
one).

-   As you should expect from Figure\~\\ref{fig.complex_numbers},
    adding two complex numbers is like adding two vectors, and
    multiplication is just like multiplying vectors. Complex numbers
    really are just a compact way of writing vectors!

<!-- -->

-   Multiplication by {{\< math \>}}i{{\< /math \>}}: If you multiply a
    complex number by {{\< math \>}}i{{\< /math \>}}, then you basically
    switch the real and imaginary parts: the real moves to the imaginary
    position, and the imaginary becomes real:
    -   {{\< math \>}} i(a + ib) = ia - b = -b + ia {{\< /math \>}}


Geometrically, this is equivalent to rotating a vector by 90 degrees! If
you do this four times, you'll end up back where you started (as you
would expect by doing a 360).

-   The complex conjugate of a complex number is just that number with
    imaginary dimension inverted:
    -   {{\< math \>}} y^\* = a - i b {{\< /math \>}}


The primary use of such a thing is to find the magnitude of a complex
number (i.e., the length of the vector that it represents), as:

-   -   {{\< math \>}} y y^\* = (a + i b)(a - i b) {{\< /math \>}}



{{\< math \>}} = a^2 - iab + iab + b^2 {{\< /math \>}}

{{\< math \>}} = a^2 + b^2 {{\< /math \>}}

This should be recognizable as simply the pythagorean theorem for the
squared length of the hypotenuse of a right triangle ({{\<
math \>}}a^2 + b^2 = c^2{{\< /math \>}}). Again, complex numbers have no
mystery: they just represent a two-valued vector.