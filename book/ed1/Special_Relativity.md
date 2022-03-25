---
title: "WELDBook Special Relativity"
---

\\begin{figure}

` \begin{center}`
`   \begin{tabular}{l}`
`     a)\\ \includegraphics[width=1.25in]{fig.lorentz_xform.id}\\ b) \\`
`     \includegraphics[width=2in]{fig.lorentz_factor.eps}`
`   \end{tabular}`
` \end{center}`
` \caption{\small Lorentz transformations.  {\bf a)} Illustration of`
`   Lorentz transformation between a static reference frame F (which is the`
`   same reference frame as the page, for example), and a frame F' moving at`
`   velocity {{< math >}}v{{< /math >}} relative to F.  Both frames contain a rigid rod, which when`
`   F' was at rest relative to F were the same length {{< math >}}l{{< /math >}}, as indicated by the`
`   ruler marks.  These rods now appear to be of different lengths in the two`
`   frames --- from the perspective of F, the rod in F' appears to have shrunk`
`   to a shorter length {{< math >}}l'{{< /math >}}.  Interestingly, from the perspective of an`
`   observer moving along with the F' reference frame, its rod appears to be`
`   of length {{< math >}}l{{< /math >}} (same as when it was stationary), and the other rod in F`
`   appears to have shrunk.  {\bf b)} The amount of shrinkage as a function of`
`   velocity {{< math >}}v{{< /math >}} is determined by the Lorentz factor {{< math >}}\gamma{{< /math >}}, which is`
`   plotted here (in natural units where the speed of light {{< math >}}c = 1{{< /math >}}).  Not`
`   much happens until you get very close to the speed of light (e.g., above`
`   90\% or .9). }`
` \label{fig.lorentz_xform}`

\\end{figure}

The mathematics of special relativity involves the computation of
relative distance and time measurements in different reference frames
that are moving relative to each other. As
Figure\~\\ref{fig.lorentz_xform}a illustrates, a rigid rod of the same
length {{\< math \>}}l{{\< /math \>}} can appear shortened if it is
moving along at a high velocity {{\< math \>}}v{{\< /math \>}} relative
to a static reference frame F (i.e., not moving relative to this page of
paper). We denote the moving rod's reference frame F'.

The factor for transforming between reference frames is the **Lorentz
factor** gamma:

-   **Lorentz factor:** {{\< math \>}} \\gamma = \\frac{1}{\\sqrt{1 -
    \\frac{v^2}{c^2}}} = \\frac{1}{\\sqrt{1 - v^2}} {{\< /math \>}}

(where the second form is in natural units, where {{\< math \>}}c=1{{\<
/math \>}}, and {{\< math \>}}v{{\< /math \>}} goes from 0 to 1). The
shape of this function is shown in Figure\~\\ref{fig.lorentz_xform}b.
Because the velocity enters into this function as a squared term, the
function has a parabolic shape, such that not much happens until the
velocity gets very close to the speed of light.

For the situation illustrated in Figure\~\\ref{fig.lorentz_xform}a, the
moving rod in frame F' appears shortened in the static frame F by a
factor of {{\< math \>}}\\frac{1}{\\gamma}{{\< /math \>}}:

-   {{\< math \>}} l' = \\frac{l}{\\gamma} {{\< /math \>}}

Similarly, the duration of a given fixed interval {{\< math \>}}t{{\<
/math \>}} (e.g., a second) in the moving reference frame F' appears
longer from the perspective of F by the same factor:

-   {{\< math \>}} t' = \\gamma t {{\< /math \>}}

It is important to keep in mind that in these equations, the {{\< math
\>}}l'{{\< /math \>}} and {{\< math \>}}t'{{\< /math \>}} refer to what
something in the moving F' reference frame looks like to someone in the
static frame, F, relative to these same quantities as measured in the
static frame ({{\< math \>}}l{{\< /math \>}} and {{\< math \>}}t{{\<
/math \>}}). But this assumes that we have previously established in a
common reference frame that the rod in F' actually has the same length
as the one in F (and the second similarly has the same duration).

An alternative (and more conventional, but sometimes more confusing) way
of using the prime notation is to directly convert between coordinate
systems of the two reference frames, where the primed and unprimed cases
both refer to *the exact same event* from the two different
perspectives. In this case {{\< math \>}}l'{{\< /math \>}} would refer
to how an observer {\\em in F'} would measure the rod length, whereas
{{\< math \>}}l{{\< /math \>}} refers to what someone in F would measure
''for the very same rod that is moving in F' '', not for the "standard
length" of the rod when both reference frames where static. In this
case, things are exactly flipped, and we would say that {{\< math
\>}}l'{{\< /math \>}} is the original rod length (say 1 meter), because
it is in the F' reference frame that the rod is not moving, whereas in
the F reference frame, the rod has shrunk to a shorter apparent length
{{\< math \>}}l{{\< /math \>}} (say .5 meters, if {{\< math
\>}}v=.866{{\< /math \>}}). Similarly, the second measured in F' ({{\<
math \>}}t'{{\< /math \>}}) corresponds to a longer time interval {{\<
math \>}}t{{\< /math \>}} in F (e.g., 2 seconds). It is definitely
complicated to keep track of all this moving back and forth between
reference frames!

\\begin{figure}

` \begin{center}`
`   \begin{tabular}{l}`
`     a)\\ \includegraphics[width=3.125in]{fig.lorentz_xform_coord.id}\\ b) \\`
`     \includegraphics[width=3.25in]{fig.lorentz_xform_coord_c.id}`
`   \end{tabular}`
` \end{center}`
` \caption{\small Lorentz coordinate transformations, plotted in one`
`   spatial coordinate (x) and time (vertical axis).  {\bf a)} In the resting`
`   frame F, two points (think of them as marbles) just sit motionless, and`
`   thus form vertical trajectories through increasing time.  When these are`
`   transformed into a reference frame F' (aligned at point (t=0,x=0) with F)`
`   moving to the left at {{< math >}}v = -.866{{< /math >}} (Lorentz factor {{< math >}}\gamma = 2{{< /math >}}), several`
`   interesting features of the Lorentz transformation are evident.  If we`
`   follow the marble that was originally located at (0,x) as it sits in frame`
`   F for 3 time steps, we see that it appears to move to the right in frame`
`   F', in the opposite direction of F' motion.  Furthermore, because of the`
`   Lorentz factor, the 3 seconds in frame F amount to 6 seconds in F', and`
`   the distance it should travel due to the relative motion, computed in`
`   frame F ({{< math >}}-vt = .866 \times 3 = 2.598{{< /math >}}) corresponds to 5.196 in frame F'.`
`   The second marble reveals a critical and somewhat counter-intuitive`
`   effect, where two events that are {\em simultaneous} in frame F (i.e., t=0`
`   for both of these), occur at {\em different times} in frame F'.`
`   Specifically the second marble sitting at rest at x=2 at t=0 is not`
```    ``encountered'' by the moving frame F' until 3.464 time seconds later (in ```
`   F' time units), due to it being offset in space from the first marble.  It`
`   takes the frame F' {{< math >}}(-vx = .866 * 2 = 1.732{{< /math >}}) time units to get to this`
`   second point (in the units of the F frame), and when this gets subject to`
`   the time dilation effect, you end up with the 3.464.  From this starting`
`   point for the second marble, the same time and space increments as for the`
`   first marble occur for the subsequent point 3 time units later.  {\bf b)}`
`   An alternative situation, where the points in frame F are now moving at`
`   the speed of light (indicated by their slopes being 1; they are now`
`   photons instead of marbles).  The Lorentz conversions preserve these`
`   slopes, so that the speeds are still 1 in the F' frame.  Thus, the speed`
`   of light is always the same to all observers.}`
` \label{fig.lorentz_xform_coord}`

\\end{figure}

In this way of doing things, in frame F, we designate an event as
occurring at space-time location {{\< math \>}}(t,x,y,z){{\< /math \>}}
(this is a **four-vector** or **space-time coordinate** in Minkowski
space, which we introduced at the end of the [EM
Chapter](/WELDBook/EM "wikilink"). In frame F', this same event has
coordinates {{\< math \>}}(t',x',y',z'){{\< /math \>}}, where the two
coordinate systems are aligned such that the origin (0,0,0,0) is the
same in both. As before, we specify that the relative velocity {{\< math
\>}}v{{\< /math \>}} between the two frames is entirely along the {{\<
math \>}}x{{\< /math \>}} axis, for simplicity. We can compute these F'
coordinates directly from our F coordinates, using Lorentz
transformations (again in natural units where {{\< math \>}}c=1{{\<
/math \>}}, and {{\< math \>}}v{{\< /math \>}} goes between 0 and 1):

-   {{\< math \>}} t' = \\gamma (t - vx) {{\< /math \>}}
-   {{\< math \>}} x' = \\gamma (x - vt) {{\< /math \>}}
-   {{\< math \>}} y' = y {{\< /math \>}}
-   {{\< math \>}} z' = z {{\< /math \>}}

Figure\~\\ref{fig.lorentz_xform_coord} shows where these formulas come
from, and demonstrates their concrete application. The {{\< math
\>}}-vx{{\< /math \>}} term in the transformation of time, and the {{\<
math \>}}-vt{{\< /math \>}} term in the transformation of the {{\< math
\>}}x{{\< /math \>}} coordinate, are critical and possibly
counter-intuitive factors in these equations. As the figure explains,
the {{\< math \>}}-vt{{\< /math \>}} is more sensible, as it simply
reflects the relative motion of the reference frame over time. The {{\<
math \>}}-vx{{\< /math \>}} term is somewhat less intuitive, but it
reflects the fact that two events separated by some spatial distance
will not be experienced as simultaneous in a moving reference frame!
Instead, the spatial separation turns into a temporal separation due to
the relative motion of the frame.

One can use these equations to compute the transformed velocity of an
object moving at velocity {{\< math \>}}w{{\< /math \>}} along the x
axis in frame F as it would appear to an observer in frame F'. We can
compute this by taking velocity as distance over time, and noting that
in time {{\< math \>}}t{{\< /math \>}} in frame F, the object will
travel a distance {{\< math \>}}x = wt{{\< /math \>}}. Thus, we need to
compute the transformed velocity as distance over time in the F' frame,
as:

-   {{\< math \>}} w' = \\frac{x'}{t'} {{\< /math \>}}


{{\< math \>}} = \\frac{\\gamma (x - v t)}{\\gamma (t - v x)} {{\<
/math \>}}

{{\< math \>}} = \\frac{\\gamma (wt - v t)}{\\gamma (t - v w t)} {{\<
/math \>}}

{{\< math \>}} = \\frac{\\gamma t (w - v)}{\\gamma t (1 - v w)} {{\<
/math \>}}

{{\< math \>}} = \\frac{w - v}{1 - wv} {{\< /math \>}}

(the intermediate steps are included to make everything as clear as
possible, tracking the substitution of {{\< math \>}}x{{\< /math \>}}
with {{\< math \>}}wt{{\< /math \>}})

Interestingly, if both velocities {{\< math \>}}w{{\< /math \>}} and
{{\< math \>}}v{{\< /math \>}} are small (relative to the speed of
light, {{\< math \>}}c=1{{\< /math \>}}), then the denominator is close
to 1, and you get the more intuitive result that the relative velocities
just add (or subtract, as the case may be). This is known as the
**Galilean** transformation, which holds for non-relativistic speeds,
and is intuitive to most people. However, as either of these speeds
increase, the denominator starts to get smaller, and the relative
velocities do not add linearly. Here are several illustrative examples
of how this equation works:

|          |         |            |                         |
|----------|---------|------------|-------------------------|
| w = 0    | w' = -v |            | only relative motion    |
| w = v    | w' = 0  |            | same speed              |
| w = .2   | v = .1  | w' = .102  | slightly faster than .1 |
| w = -.1  | v = .1  | w' = .199  | slightly slower than .2 |
| w = .9   | v = .1  | w' = .87   | much faster than .8     |
| w = -.9  | v = .1  | w' = .99   | much slower than 1.1    |
| w = 1.0  | v = .1  | w' = 1.0   | speed of light is same  |
| w = -1.0 | v = .1  | w' = 1.0 & | speed of light is same  |

One other important point to be made about special relativity is that
there is an invariant calculation that can be made on the coordinates
measured in any given reference frame, which will yield the same result
as in any other reference frame. This is a kind of distance metric
between two points {{\< math \>}}(t_1, x_1, y_1, z_1){{\< /math \>}}
and {{\< math \>}}(t_2, x_2, y_2, z_2){{\< /math \>}} (both of which
must be measured in the same reference frame):

-   {{\< math \>}} ds^2 = (t_1 - t_2)^2 - (x_1 - x_2)^2 - (y_1 -
    y_2)^2 - (z_1 - z_2)^2 {{\< /math \>}}

You can try this out on the coordinates in
Figure\~\\ref{fig.lorentz_xform_coord} for the same points in the
different reference frames: you'll get the same results for either (with
small differences due to round-off errors). Interestingly, when you try
it for the second case with the photons moving at the speed of light,
you see that this value is always 0. Thus, in effect, the distance in
space is equal to the distance in time. If we just have motion in one
spatial dimension (e.g., {{\< math \>}}x{{\< /math \>}}), this is clear:

-   {{\< math \>}} (t_1 - t_2)^2 - (x_1 - x_2)^2 = 0 {{\< /math \>}}


{{\< math \>}} (t_1 - t_2)^2 = (x_1 - x_2)^2 {{\< /math \>}}

This is exactly the same time = space relationship that we discussed
earlier for the basic wave equation. Perhaps now the fundamental
importance of this for relativity is clearer.

This distance metric also tells you in what way two events are
separated. If the distance metric is positive, then the two points are
separated by time, and if it is negative, they are separated by space.

Interestingly, the Lorentz transformations can be derived directly from
this distance metric, and this distance metric can in turn be derived
from the principle that the speed of light is a constant in any
reference frame. Therefore, all of these effects are really just
different manifestations of the same basic set of constraints, which are
captured directly and automatically in the wave equations.

One additional property of special relativity has to do with the
relationship between energy and momentum. If an object is at rest, its
only energy is that associated with its rest mass, according to the
famous equation:

-   {{\< math \>}} E_0 = m_0 c^2 {{\< /math \>}}

As the object moves faster, it gains energy in proportion to the Lorentz
factor {{\< math \>}}\\gamma{{\< /math \>}}:

-   {{\< math \>}} E = \\gamma m_0 c^2 {{\< /math \>}}

Furthermore, the relativistic momentum of this object is just the
Lorentz factor times the standard Newtonian definition of momentum for
motion at velocity {{\< math \>}}\\vec{v}{{\< /math \>}}:

-   {{\< math \>}} \\vec{p} = \\gamma m_0 \\vec{v} {{\< /math \>}}

These two variables can be related in the relativistic energy-momentum
equation:

-   {{\< math \>}} E^2 = \\vec{p}^2 c^2 + (m_0 c^2)^2 {{\< /math \>}}


{{\< math \>}} E = \\sqrt{\\vec{p}^2 c^2 + (m_0 c^2)^2} {{\< /math \>}}

which is different way of expressing the energy of the system. It is
very sensible, in that the two main contributors to energy are the
momentum (i.e., kinetic energy) and the rest energy. If you set {{\<
math \>}}c=1{{\< /math \>}}, it is even simpler:

-   {{\< math \>}} E^2 = \\vec{p}^2+ m_0^2 {{\< /math \>}}
-   {{\< math \>}} E = \\sqrt{\\vec{p}^2+ m_0^2} {{\< /math \>}}

You can think of the rest energy and momentum as two legs of a right
triangle, such that the total energy is the hypotenuse, according to the
pythagorean theorem.

In the limit of a slow velocity (relative to the speed of light), this
expression approaches the Newtonian expression for kinetic energy (plus
the rest mass energy):

-   {{\< math \>}} E \\approx \\frac{1}{2}m_0 \\vec{v}^2 + m_0 c^2
    {{\< /math \>}}

We will return to the above energy expression a bit later, where we'll
find that we can actually derive the KG wave equation directly from it!

Finally, we note that the warping of space and time that produces
gravitational effects according to general relativity enters into our
model in a very different way, as described later. Thus, in our model,
special and general relativity result from two very different
mechanisms.