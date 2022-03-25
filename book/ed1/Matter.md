---
title: "WELDBook Matter"
---

Historically, matter has typically been conceived of as something hard
and solid: a particle of some form or another. The classical picture of
the atom, with little planet-like electron particles orbiting around the
sun-like nucleus (composed of proton and neutron particles), is a good
example. However, in 1924, de Broglie discovered that matter also has
wave-like properties. As this particle-vs-wave debate developed in
quantum physics, it became clear that matter exhibits both kinds of
properties, and people have tried to come to terms with some kind of
simultaneous duality of wave and particle aspects to matter. Indeed,
this duality extends even to things that originally seemed very much
more wave-like than particle-like, such as electromagnetic radiation
(light).

Our ultimate model will consist entirely of waves, with all
particle-like effects emerging out of the dynamic interactions between
wave systems. This is the most controversial and unproven aspect of our
model. Nevertheless, we are basically forced into this conclusion by a
tidal wave of support for a purely wave-based framework, with no really
compelling reason to include discrete, hard particles as such. Indeed,
one can view much of the confusion associated with quantum physics as
just a stubborn inability to let go of the particle model of matter.
Once we dispense with these particles entirely, much of the confusion
melts away. We are left with a few particle-like phenomena to account
for, but we can provide a very plausible (if currently unproven)
explanation for them. The full discussion of these issues will come
later.

\\subsection{Problems with Particles}

First, let's consider for a moment the possibility that, within our
cellular automaton system, matter is composed in some way of particles.
How natural or easy is it to get that to work? It turns out, it is not
very natural or easy at all, for much the same reason that purely binary
or discrete states are not particularly natural in the CA system.
Specifically, the most obvious way of introducing a particle in this
system is to imagine that it is a discrete binary state value in a cubic
cell. For all locations where there are no particles, this state value
is 0, and where there are particles, it is 1. The problem is, how do
these particles move? They can only make discrete jumps to one of the 26
neighboring cells. How can they exhibit trajectories of motion that are
not along one of these 26 directions? How can they take on different
velocities? They would have to wait in one spot for a while, then make a
discrete jump, etc, with the ratio of waiting to jumping corresponding
to velocity. But what provides the \`\`memory'' for how long to wait
before jumping, and what direction to jump to? In more technical terms,
what provides the momentum representation for such a particle?

Another important problem with the particle model is that it introduces
complications for force fields very near the particle itself. Both the
electromagnetic and gravitational forces follow a {{\< math
\>}}1/r^2{{\< /math \>}} law, which means that the strength of these
forces in the cells immediately adjacent to a discrete particle would be
very strong, especially for the much stronger electromagnetic force.
This is problematic because such a strong level of force corresponds to
a very high energy density, which can end up producing unexpected
physics. For example, high energies can spontaneously create new massive
particles. A wave-like distributed particle model would avoid such
problems, by distributing the source of such forces over a much wider
area, and greatly reducing the charge and mass density per unit cube.

% todo: do the math on this, show what the energy would be, etc.

Some of these problems may be surmountable, but the level of complexity
and mechanism required to do it is daunting. For example, I have
implemented a system for solving the particle motion problem, but it is
truly baroque in its complexity and implausibility. Again, we cannot
place strong a priori constraints on what happens at the most
fundamental level, so it could be that particles of this sort exist. But
perhaps we should pursue the wave alternative first, to see if something
more natural emerges. Indeed, we'll see in a moment that a single
modification to the basic wave equation produces a surprisingly
comprehensive description of matter (while still falling short of
describing actual physics). The resulting model is so simple, elegant,
and consistent with known physics that we do not hesitate to completely
abandon the discrete particle model, with all of its difficulties and
complexity.

\\subsection{Klein-Gordon Waves}

\\begin{figure}

` \centering\includegraphics[height=1.25in]{fig.wave_packet.eps}`
` \caption{\small A wave packet, which is a spatially localized wave`
`   disturbance that propagates through space as a coherent entity.  The two`
`   values shown here are the state value and the first derivative --- the`
`   relationship between these two determines which direction the wave`
`   travels. This is our model for a particle.  Mathematically, it can be`
`   constructed by multiplying a Gaussian function (normal bell-shaped`
`   distribution curve) times a sine wave.}`
` \label{fig.wave_packet}`

\\end{figure}

In beginning to explore the wave model of matter, we need to first
establish a few basic concepts of what it would even mean for a particle
to be described by a wave. The main idea is that a particle corresponds
to a {\\em wave packet}, which is a spatially localized wave disturbance
(see Figure\~\\ref{fig.wave_packet}). It can act like a particle in
that it is somewhat spatially localized, and moves as a coherent entity.
If you zoomed out very far, and blurred your eyes, you could imagine
that a wave packet would look like a tiny point particle. Nevertheless,
it fundamentally acts like a wave, in the sense that it is actually made
of oscillations, and obeys a wave equation. As to what exactly the wave
material is and what it means for observations, we'll postpone for
later. At this point, we'll content ourselves with this level of
description, and just start developing some new twists on the basic wave
equation; we'll return to the thorny interpretational issues (e.g.,
wave-particle duality, probabilistic interpretation of the wave, etc),
once we have a better sense of how these new waves behave.

Recall that the wave equation can be written as a second-order
differential equation (equation\~\\ref{eq.lapl_wave}):

-   {{\< math \>}}

` \frac{\partial^2 {\varphi}}{\partial t^2} = \nabla^2 \varphi \non`

{{\< /math \>}} Note that we've introduced a new variable here, {{\<
math \>}}\\varphi{{\< /math \>}}, which is a variant of the Greek
\`\`phi'' symbol called \`\`varphi'', which is often used for wave
functions of particles. We'll always use this variable to represent a
single scalar state variable, that updates according to a modified wave
function representing a massive particle.

\\begin{figure}

` \centering\includegraphics[width=3in]{fig.kg_mass_drag.id}`
` \caption{\small The additional mass term {{< math >}}-m_0^2 \varphi{{< /math >}} in the`
```    Klein-Gordon (KG) wave equation ``drags down'' the wave in proportion to ```
`   the height of the waves (i.e., amplitude away from zero, either positive`
```    or negative).  This fights against the ``curvature'' of the wave, computed ```
`   by {{< math >}}\nabla^2{{< /math >}}.  Higher frequency waves have higher curvature, and thus move`
`   faster than lower frequency waves.}`
` \label{fig.kg_mass_drag}`

\\end{figure}

So, what if we add a single new term to this equation, where we subtract
away some \`\`mass'' ({{\< math \>}}m_0{{\< /math \>}}, a constant)
from the laplacian ({{\< math \>}}\\nabla^2 \\varphi{{\< /math \>}})
\`\`curvature'' driving force term (Figure\~\\ref{fig.kg_mass_drag}):

-   {{\< math \>}}

` \frac{\partial^2 {\varphi}}{\partial t^2} = \nabla^2 \varphi - m_0^2 \varphi`

{{\< /math \>}} or, in somewhat simpler notation that we'll use more
frequently:

-   {{\< math \>}}

` \boxed{\frac{\partial^2 {\varphi}}{\partial t^2} = (\nabla^2 - m_0^2) \varphi}`
` \label{eq.kg}`

{{\< /math \>}}

Schrödinger

This new equation is called the {\\em Klein-Gordon (KG)} equation, named
after Oskar Klein and Walter Gordon, who published the first papers on
it (\\nopcite{Klein26,Gordon27}; see \\incite{Kragh84} for a detailed
history of this equation, which was actually discovered by many
individuals, including Schrödinger). It captures a surprising number of
important phenomena, as we detail next. However, it needs a few more
bells and whistles (namely charge and spin) in order to actually
describe a known particle, such as an electron.

First, we'll introduce some variations on how to write this equation,
which are all obviously identical to the KG equation given above, but
highlight different features of it, as we'll see more later. Here's one
such variation:

-   {{\< math \>}}

` \frac{\partial^2 {\varphi}}{\partial t^2} - \nabla^2\varphi = -m_0^2 \varphi`

{{\< /math \>}} and another:

-   {{\< math \>}}

` \left(\frac{\partial^2 {}}{\partial t^2} - \nabla^2 + m_0^2\right) \varphi = 0`

{{\< /math \>}} These last two forms are useful for relating to the
four-vector version of the wave equation, where we saw that
(equation\~\\ref{eq.covgrcongr}):

-   {{\< math \>}}

` \partial_\mu \partial^\mu = \frac{\partial^2 {}}{\partial t^2} - \nabla^2`

{{\< /math \>}} so that the equation can be written:

-   {{\< math \>}}

` \partial_\mu \partial^\mu \varphi = - m_0^2 \varphi`
` \label{eq.kg_4vm}`

{{\< /math \>}} or:

-   {{\< math \>}}

` \left(\partial_\mu \partial^\mu + m_0^2\right) \varphi = 0`
` \label{eq.kg_4v}`

{{\< /math \>}}

Finally, if we do not have natural units where {{\< math \>}}c = \\hbar
= 1{{\< /math \>}}, the equation has a few more parameters:

-   {{\< math \>}}

` \frac{\partial^2 {\phi}}{\partial t^2} = c^2 \left(\nabla^2 - \frac{m_0^2 c^2}{\hbar^2}\right)\phi`
` \label{eq.kg_full}`

{{\< /math \>}} where {{\< math \>}}\\hbar = \\frac{h}{2\\pi}{{\< /math
\>}} and {{\< math \>}}h{{\< /math \>}} is Plank's constant (which we'll
hear more about in a moment).

To actually implement this KG equation in our cellular automaton model,
we make one modification to the acceleration term, to subtract off the
mass:

-   {{\< math \>}}

` \boxed{\ddot \varphi_i^{t+1} = \frac{3}{13}\sum_{j \in {\cal N}_{26}} k_j (\varphi_j`
` - \varphi_i) - m_0^2 \varphi_i}`

{{\< /math \>}}

\\subsection{Variable Speeds: Momentum = Frequency}

\\begin{figure}

` \centering\includegraphics[width=3.15in]{fig.kg_freq_speed.id}`
` \caption{\small Relationship between frequency and speed in the`
`   Klein-Gordon (KG) wave function, which derives from competition between`
`   mass drag and overall curvature of the wave, as computed by {{< math >}}\nabla^2{{< /math >}}.`
`   Higher frequency waves have more curvature and thus move faster.}`
` \label{fig.kg_freq_speed}`

\\end{figure}

Perhaps the most important feature of this KG equation is that waves now
travel at {\\em variable speeds}, instead of always moving at exactly
the same speed. This speed now depends on the relationship between the
curvature ({{\< math \>}}\\nabla^2 \\varphi{{\< /math \>}}) and the
squared-mass value {{\< math \>}}m_0^2 \\varphi{{\< /math \>}}. In
essence, the mass \`\`drags down'' the wave propagation force conveyed
by the local curvature, {{\< math \>}}\\nabla^2 \\varphi{{\< /math \>}}
(Figure\~\\ref{fig.kg_mass_drag}). Therefore, to get the wave to move
faster, you need more curvature, which is to say, a higher frequency
wave, because higher frequency waves have more waves per unit length,
and this means overall greater \`\`curvature''
(Figure\~\\ref{fig.kg_freq_speed}).

This relationship between frequency {{\< math \>}}f{{\< /math \>}} of a
wave and the velocity of the particle that it describes is captured in
one of the most basic equations of quantum physics:

-   {{\< math \>}}

` p & = & \frac{h}{c} f \non \\ m v & = & \frac{h}{c} f \non \\ v & = &`
` \frac{h}{c m} f`

{{\< /math \>}} where {{\< math \>}}p = mv{{\< /math \>}} is the
momentum, {{\< math \>}}m{{\< /math \>}} is the mass of the particle,
{{\< math \>}}v{{\< /math \>}} is the velocity, and {{\< math \>}}h{{\<
/math \>}} is Planck's constant. This can also be written in terms of
the wavelength {{\< math \>}}\\lambda{{\< /math \>}}, which is the
inverse of the frequency:

-   {{\< math \>}}

` f & = & \frac{c}{\lambda} \non \\ \lambda & = & \frac{c}{f} \non \\ \lambda`
` f & = & c`

{{\< /math \>}} so that momentum is inversely proportional to the length
of the waves:

-   {{\< math \>}}

` p = \frac{h}{\lambda}`

{{\< /math \>}}

As we will explore in greater detail later, the momentum can be computed
directly from the wave function in terms of the first-order spatial
derivative or gradient:

-   {{\< math \>}}

` p \propto \vec{\nabla} \varphi`

{{\< /math \>}} where this spatial gradient is again going to be greater
overall as the wave frequency increases, as suggested by the quantum
mechanical relationships above.

Again, the main point for now is just that introducing the mass term
makes the relative curvature or frequency of the wave matter in
determining the overall velocity or momentum of the wave packet that
describes a particle. Without this mass term, all waves travel at the
speed of light.

\\subsection{Newtonian Mechanics}

We can intuitively see that this very simple modification to the wave
equation captures all of classical (Newtonian) mechanics for a
\`\`particle'' characterized by a wave according to this equation. In
the absence of any external forces, the wave will propagate along at a
constant velocity (Newton's first law of inertia), because the frequency
of the wave does not decrease (and it would not change its overall
direction of propagation). If a force is applied to this system, it will
change the frequency of the oscillation of the wave, and thus result in
a change in momentum, in accord with Newton's second law:

-   {{\< math \>}}

` F = \frac{\partial {\vec{p}}{\partial t}} = m \frac{\partial {\vec{v}}{\partial t}} = m \vec{a}`

{{\< /math \>}}

After a few more developments, we can make this relationship much more
formally accurate and precise, by considering the overall energy and
momentum relationships computed by the KG wave equation. We will see
that Schrödinger's equation, which is the primary wave equation for
basic quantum physics, captures classical Newtonian physics, and that
the KG equation is a version of Schrödinger's equation that also takes
into account special relativity, which is important when particles are
moving very fast (i.e., relatively close to the speed of light).

Anticipating these results, and relying on intuition for now, we see
that with one tiny addition, we now have an equation that can describe
the motion of a massive particle through space (e.g., as a wave packet),
in agreement with all the known physical laws (i.e., quantum physics and
special relativity, which reduce in certain cases to the more familiar
Newtonian mechanics).

\\subsection{What is the Mass?}

The value {{\< math \>}}m_0{{\< /math \>}} in the KG equation is the
{\\em rest mass} of the particle that it describes (the 0 subscript
indicates \`\`rest''). It is a fixed, constant value for a given type of
particle, and thus we can easily imagine that it is just built into the
equations for the state variables that characterize that type of
particle.

For an electron, this mass is {{\< math \>}}9.1x10^{-28}{{\< /math \>}}
grams, which is an extremely tiny weight. Interestingly in the natural
units of our model (known as Planck's units), this is still a very small
number: {{\< math \>}}4.18x10^{-23}{{\< /math \>}}. This means that the
mass doesn't put that much of a drag on the movement of electron waves.

The value of {{\< math \>}}m_0{{\< /math \>}} also defines the {\\em
Compton wavelength} of a given particle, which is the wavelength of a
particle at rest, due strictly to the rest mass. The formula for the
Compton wavelength {{\< math \>}}\\lambda_C{{\< /math \>}} is:

-   {{\< math \>}}

` \lambda_C = \frac{h}{m_0 c}`

{{\< /math \>}} and in our natural units where {{\< math \>}}h = c =
1{{\< /math \>}},

-   {{\< math \>}}

` \lambda_C = \frac{1}{m_0}`

{{\< /math \>}}

The Compton wavelength of an electron in the natural units of our system
is {{\< math \>}}2.39x10^{22}{{\< /math \>}} cubes, which is a very
large number of cubes indeed. This means that your basic electron is
very, very spread out from the perspective of our Planck-scale model.
One consequence of this is that it doesn't take a very high frequency to
get the electron moving above this low baseline value. One might imagine
that this gives the system plenty of room for electrons to go faster: if
their rest mass were significantly larger, their rest wavelengths would
be smaller, and there wouldn't be as much additional room to go faster
by having smaller wavelengths and thus higher frequencies.

`Note that this is a particular issue that arises in our discrete space model:`

if you imagine that space is continuously divisible, then frequencies
can get infinitely high, and you don't really need to worry about the
overall magnitude of the rest mass. This also represents a potentially
testable prediction of the model: there is a fixed upper limit to how
high wave frequencies can go (i.e., a wavelength of one cube length).
However, this represents such a fantastically large amount of energy
that it may never be attainable in practice.

One other thing about the rest mass --- we can consider what happens
when you set the rest mass of our particle to zero. You should see that
we immediately recover the basic wave equation from before. Thus, it is
immediately obvious that \`\`particles'' with a zero rest mass must move
at the speed of light. This is a basic postulate of special relativity.
Note also that it is impossible for a massive particle to travel at the
speed of light, because it would have to have an infinitely high
frequency, and this is not possible (even in a continuous spatial
model).

\\subsection{Smooth, Continuous Motion}

As a continuous-valued second-order wave equation, the KG equation still
has all of the advantages discussed earlier about making the underlying
grid disappear. Furthermore, it easily and naturally allows us to
describe continuously variable rates of speed, in terms of continuous
variation in the frequency or wavelength of wave oscillation. Particles
described by such an equation can also travel in any direction, because
of the essentially perfect spatial symmetry of wave propagation
exhibited by this equation.

In contrast, models with a discrete particle suffer from all manner of
complexity in overcoming such problems. Thus, by describing a particle
exclusively using this wave equation, we avoid many difficulties, and it
remains to be seen if we encounter any other problems.

\\subsection{Special Relativity}

As we noted before, the wave equation automatically satisfies special
relativity. This is still true of the KG equation, which is why it is
known as the relativistic version of Schrödinger's equation. Indeed,
because the KG equation describes a massive particle, it opens up the
much more interesting set of issues with special relativity having to do
with time and space contracting and expanding.

Apparently Einstein was motivated to come up with special relativity in
part by thinking about what it would be like to catch up with a beam of
light. Turns out you can't: light always moves at the same speed away
from you, no matter how fast you are going. Thus, the waves described by
the basic wave equation are always speeding along at the same speed, and
are relativistic in a fairly straightforward but also somewhat
uninteresting way: they just cruise around at the same speed of light,
and not much else can be said for them.

In contrast, things that have a non-zero rest mass are subject to three
major effects as their velocities increase (all of these are as measured
relative to a static observer watching such a thing whiz by --- in our
model, we can conveniently use the underlying grid reference frame):
\\begin{itemize} \\item They shrink along the direction of travel
(Lorentz contraction). \\item Time slows down (time dilation). \\item
Apparent (relativistic) mass increases. \\end{itemize}

\\begin{figure}

` \centering\includegraphics[width=3.15in]{fig.wave_contract.id}`
` \caption{\small Intuitive explanation of Lorentz contraction of`
`   space that occurs as something moves faster, in terms of the relationship`
`   between wave frequency and speed in the Klein-Gordon wave equation.`
`   Because faster movement is associated with higher frequency and shorter`
`   wavelength, the system contracts in the direction of motion as it speeds`
`   up.  Thus, any measurements made in the faster system will have their`
`   basic constituents, including yard sticks and everything else, shrunk in`
`   this way.  This is one of the main effects of special relativity.}`
` \label{fig.wave_contract}`

\\end{figure}

Almost miraculously, all of these effects can be derived directly from
the basic KG equation. Intuitively, the contraction of space along the
direction of travel occurs because the length of a given thing is
measured in terms of the wavelengths of the underlying particles that
compose it. As these things move with greater velocity, their frequency
increases and their wavelengths decrease, and this results in a shorter
overall length (as viewed from an outside observer)
(Figure\~\\ref{fig.wave_contract}). Similarly, the increase in apparent
mass comes from the increased difficulty in further accelerating the
system. Mass is measured in terms of the inertia of a system: its
resistance to further acceleration. It happens that the amount of force
required to increase the frequency of a given wave packet further is
proportional to its existing frequency, so that it becomes harder and
harder to accelerate something as it moves faster and faster. This is
manifest as an increase in the apparent mass of the particle. The
increase in apparent mass of the particle also has the effect of causing
the apparent time to slow down: time is fundamentally measured as a rate
of change, which depends on accelerations, which are affected by the
increase in apparent mass.

The very stretchiness and malleability of space and time postulated by
special relativity is a very strong argument in favor of waves over
particles. Waves are inherently stretchy and malleable (as just invoked
above to explain the key features of special relativity), whereas
particles as hard discrete points just don't seem to fit with this
picture. What would it mean for a point particle to contract along its
direction of travel?

One of the main puzzles that people often have with special relativity
is understanding how light can appear to move at the same fixed speed,
when an observer is screaming along at nearly the speed of light. You
would think that you would \`\`catch up'' to a photon (as in Einstein's
motivating thought experiment), and even if you couldn't see it actually
standing still, it sure should seem to move more slowly relative to a
speeding observer than to someone \`\`sitting still''. The trick is, as
an observer speeds up, the time dilation and space contraction effects
conspire to alter the perception of the relative motion of other things.
The wavelength and velocity of the moving light wave never actually
change (they are always the same relative to the underlying reference
frame of the grid), but relative to the moving observer, they appear to
be much faster. This is because the observer's rulers have shrunk, and
their clocks have slowed down, so that the same light wave appears to be
moving much faster to them. In contrast, a static observer watching the
moving observer chasing after the light beam will perceive the two as
having a smaller relative velocity difference. These changes occur in
exactly the right way to make the light wave appear to travel at the
speed of light to the moving observer (which in fact it is). The next
section gives these basic intuitions some mathematical precision.

\\subsubsection{Mathematics of Special Relativity}

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
to a \`\`static'' reference frame F (i.e., not moving relative to this
page of paper). We denote the moving rod's reference frame F'.

The factor for transforming between reference frames is the {\\em
Lorentz

` factor}:`

-   {{\< math \>}}

` \gamma = \frac{1}{\sqrt{1 - \frac{v^2}{c^2}}} = \frac{1}{\sqrt{1 - v^2}}`
` \label{eq.lorentz_factor}`

{{\< /math \>}} (where the second form is in natural units, where {{\<
math \>}}c=1{{\< /math \>}}, and {{\< math \>}}v{{\< /math \>}} goes
from 0 to 1). The shape of this function is shown in
Figure\~\\ref{fig.lorentz_xform}b. Because the velocity enters into
this function as a squared term, the function has a parabolic shape,
such that not much happens until the velocity gets very close to the
speed of light.

For the situation illustrated in Figure\~\\ref{fig.lorentz_xform}a, the
moving rod in frame F' appears shortened in the static frame F by a
factor of {{\< math \>}}\\frac{1}{\\gamma}{{\< /math \>}}:

-   {{\< math \>}}

` l' = \frac{l}{\gamma}`

{{\< /math \>}} Similarly, the duration of a given fixed interval {{\<
math \>}}t{{\< /math \>}} (e.g., a second) in the moving reference frame
F' appears longer from the perspective of F by the same factor:

-   {{\< math \>}}

` t' = \gamma t`

{{\< /math \>}} It is important to keep in mind that in these equations,
the {{\< math \>}}l'{{\< /math \>}} and {{\< math \>}}t'{{\< /math \>}}
refer to what something in the moving F' reference frame looks like to
someone in the static frame, F, relative to these same quantities as
measured in the static frame ({{\< math \>}}l{{\< /math \>}} and {{\<
math \>}}t{{\< /math \>}}). But this assumes that we have previously
established in a common reference frame that the rod in F' actually has
the same length as the one in F (and the second similarly has the same
duration).

An alternative (and more conventional, but sometimes more confusing) way
of using the prime notation is to directly convert between coordinate
systems of the two reference frames, where the primed and unprimed cases
both refer to {\\em the exact same event} from the two different
perspectives. In this case {{\< math \>}}l'{{\< /math \>}} would refer
to how an observer {\\em in F'} would measure the rod length, whereas
{{\< math \>}}l{{\< /math \>}} refers to what someone in F would measure
{\\em for the very same rod that is moving in F'}, not for the
\`\`standard length'' of the rod when both reference frames where
static. In this case, things are exactly flipped, and we would say that
{{\< math \>}}l'{{\< /math \>}} is the original rod length (say 1
meter), because it is in the F' reference frame that the rod is not
moving, whereas in the F reference frame, the rod has shrunk to a
shorter apparent length {{\< math \>}}l{{\< /math \>}} (say .5 meters,
if {{\< math \>}}v=.866{{\< /math \>}}). Similarly, the second measured
in F' ({{\< math \>}}t'{{\< /math \>}}) corresponds to a longer time
interval {{\< math \>}}t{{\< /math \>}} in F (e.g., 2 seconds). It is
definitely complicated to keep track of all this moving back and forth
between reference frames!

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
(this is a {\\em four-vector} or {\\em space-time coordinate} in
Minkowski space, which we mentioned earlier). In frame F', this same
event has coordinates {{\< math \>}}(t',x',y',z'){{\< /math \>}}, where
the two coordinate systems are aligned such that the origin (0,0,0,0) is
the same in both. As before, we specify that the relative velocity {{\<
math \>}}v{{\< /math \>}} between the two frames is entirely along the
{{\< math \>}}x{{\< /math \>}} axis, for simplicity. We can compute
these F' coordinates directly from our F coordinates, using Lorentz
transformations (again in natural units where {{\< math \>}}c=1{{\<
/math \>}}, and {{\< math \>}}v{{\< /math \>}} goes between 0 and 1):

-   {{\< math \>}}

` t' & = & \gamma (t - vx) \non\\ x' & = & \gamma (x - vt) \non\\ y' & = & y`
` \non\\ z' & = & z`

{{\< /math \>}} Figure\~\\ref{fig.lorentz_xform_coord} shows where
these formulas come from, and demonstrates their concrete application.
The {{\< math \>}}-vx{{\< /math \>}} term in the transformation of time,
and the {{\< math \>}}-vt{{\< /math \>}} term in the transformation of
the {{\< math \>}}x{{\< /math \>}} coordinate, are critical and possibly
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

-   {{\< math \>}}

` w' & = & \frac{x'}{t'} \non \\ & = & \frac{\gamma (\boxed{x} - v t)}{\gamma`
` (t - v \boxed{x})} \non \\ & = & \frac{\gamma (\boxed{wt} - v t)}{\gamma (t`
` - v \boxed{w t})} \non \\ & = & \frac{\gamma t (w - v)}{\gamma t (1 - v w)}`
` \non \\ & = & \frac{w - v}{1 - wv}`

{{\< /math \>}} (the intermediate steps are included to make everything
as clear as possible, and the substitution of {{\< math \>}}x{{\< /math
\>}} with {{\< math \>}}wt{{\< /math \>}} is highlighted with the
boxes).

Interestingly, if both velocities {{\< math \>}}w{{\< /math \>}} and
{{\< math \>}}v{{\< /math \>}} are small (relative to the speed of
light, {{\< math \>}}c=1{{\< /math \>}}), then the denominator is close
to 1, and you get the more intuitive result that the relative velocities
just add (or subtract, as the case may be). This is known as the {\\em
Galilean} transformation, which holds for non-relativistic speeds, and
is intuitive to most people. However, as either of these speeds
increase, the denominator starts to get smaller, and the relative
velocities do not add linearly. Here are several illustrative examples
of how this equation works:

-   {{\< math \>}}

` w = 0: & w' = -v & \mbox{(only relative motion)} \non \\ w = v: & w' = 0 &`
` \mbox{(same speed)} \non \\ w = .2, v = .1: & w' = .102 & \mbox{(slightly`
` faster than .1!)} \non \\ w = -.1, v = .1: & w' = .199 & \mbox{(slightly`
` slower than .2!)} \non \\ w = .9, v = .1: & w' = .87 & \mbox{(much faster`
` than .8!)} \non \\ w = -.9, v = .1: & w' = .99 & \mbox{(much slower than`
` 1.1!)} \non \\ w = 1.0, v = .1: & w' = 1.0 & \mbox{(speed of light is`
` same!)} \non \\ w = -1.0, v = .1: & w' = 1.0 & \mbox{(speed of light is`
` same!)} \non \\`

{{\< /math \>}}

One other important point to be made about special relativity is that
there is an invariant calculation that can be made on the coordinates
measured in any given reference frame, which will yield the same result
as in any other reference frame. This is a kind of distance metric
between two points {{\< math \>}}(t_1, x_1, y_1, z_1){{\< /math \>}}
and {{\< math \>}}(t_2, x_2, y_2, z_2){{\< /math \>}} (both of which
must be measured in the same reference frame):

-   {{\< math \>}}

` ds^2 = (t_1 - t_2)^2 - (x_1 - x_2)^2 - (y_1 - y_2)^2 - (z_1 - z_2)^2`

{{\< /math \>}} You can try this out on the coordinates in
Figure\~\\ref{fig.lorentz_xform_coord} for the same points in the
different reference frames: you'll get the same results for either (with
small differences due to round-off errors). Interestingly, when you try
it for the second case with the photons moving at the speed of light,
you see that this value is always 0. Thus, in effect, the distance in
space is equal to the distance in time. If we just have motion in one
spatial dimension (e.g., {{\< math \>}}x{{\< /math \>}}), this is clear:

-   {{\< math \>}}

` (t_1 - t_2)^2 - (x_1 - x_2)^2 & = & 0 \non \\ (t_1 - t_2)^2 & = & (x_1 -`
` x_2)^2`

{{\< /math \>}} This is exactly the same time = space relationship that
we discussed earlier for the basic wave equation. Perhaps now the
fundamental importance of this for relativity is clearer.

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

-   {{\< math \>}}

` E_0 = m_0 c^2`

{{\< /math \>}} which incidentally is somewhat more direct but perhaps
less interesting in natural units where {{\< math \>}}c=1{{\< /math
\>}}:

-   {{\< math \>}}

` E_0 = m_0`

{{\< /math \>}} As the object moves faster, it gains energy in
proportion to the Lorentz factor {{\< math \>}}\\gamma{{\< /math \>}}:

-   {{\< math \>}}

` E = \gamma m_0 c^2`

{{\< /math \>}} Furthermore, the relativistic momentum of this object is
just the Lorentz factor times the standard Newtonian definition of
momentum for motion at velocity {{\< math \>}}\\vec{v}{{\< /math \>}}:

-   {{\< math \>}}

` \vec{p} = \gamma m_0 \vec{v}`

{{\< /math \>}}

These two variables can be related in the relativistic energy-momentum
equation:

-   {{\< math \>}}

` E^2 & = & \vec{p}^2 c^2 + (m_0 c^2)^2 \non \\ E & = & \sqrt{\vec{p}^2 c^2 +`
` (m_0 c^2)^2}`
` \label{eq.rel_e}`

{{\< /math \>}} which is different way of expressing the energy of the
system. It is very sensible, in that the two main contributors to energy
are the momentum (i.e., kinetic energy) and the rest energy. If you set
{{\< math \>}}c=1{{\< /math \>}}, it is simpler:

-   {{\< math \>}}

` E^2 & = & \vec{p}^2+ m_0^2 \non \\ E & = & \sqrt{\vec{p}^2+ m_0^2}`

{{\< /math \>}} You can think of the rest energy and momentum as two
legs of a right triangle, such that the total energy is the hypotenuse,
according to the pythagorean theorem.

In the limit of a slow velocity (relative to the speed of light), this
expression approaches the Newtonian expression for kinetic energy (plus
the rest mass energy):

-   {{\< math \>}}

` E \approx \frac{1}{2}m_0 \vec{v}^2 + m_0 c^2`

{{\< /math \>}} We will return to the above energy expression a bit
later, where we'll find that we can actually derive the KG wave equation
directly from it!

Finally, we note that the warping of space and time that produces
gravitational effects according to general relativity enters into our
model in a very different way, as described later. Thus, in our model,
special and general relativity result from two very different
mechanisms.

\\subsection{Relationship to Schrödinger's Equation}

As many readers are likely aware, Schrödinger's equation provides the
cornerstone of quantum physics. This equation describes the evolution of
a particle wave over time. A wave of what? The standard interpretation
is that it is a wave of {\\em probability}, in the sense that the
\`\`square'' (complex conjugate) of the wave values correspond to the
probability of finding a particle in a given location.

Schrödinger's equation is a challenge for many people to understand, in
part because it requires complex numbers to express. This is because it
is a first order differential equation. In general, wave-like behavior
can either be described by a second-order equation involving normal
scalar variables (as we've been using), or it can be described by a
first-order equation involving complex numbers. In the first-order
version, you have two variables for every one variable in the
second-order one --- we'll see later that this fact allows us to use
only four variables to represent an electron using a second-order wave
equation, whereas the standard first-order Dirac equation requires
eight. The general intuition is that a first-order wave equation
involves motion as rotation among its complex variables, in addition to
motion through space, whereas the second-order equation just has motion
through space. This will be clearer as we examine Schrödinger's equation
more closely.

Before we do so, we provide a review of complex numbers for those who
may not be particularly familiar with them. Complex numbers are
important for understanding Schrödinger's equation (as described
thereafter), and for subsequent developments of the KG equation, which
requires complex numbers to represent a conserved charge value.

\\subsubsection{Complex Numbers}

\\begin{figure}

` \centering\includegraphics[height=1.5in]{fig.complex_numbers.id}`
` \caption{\small Complex numbers are just a way of representing two`
`   real values with one number, where these two values are aligned along two`
`   separate orthogonal dimensions.  The imaginary number {{< math >}}i{{< /math >}}, where {{< math >}}i^2 =`
`   -1{{< /math >}}, is what keeps these two values orthogonal --- the first value {{< math >}}a{{< /math >}} is`
`   along the real axis, and the second value {{< math >}}b{{< /math >}} is along the imaginary axis.`
`   The complex conjugate, {{< math >}}c^*{{< /math >}}, is simply subtracting the imaginary part`
```    instead of adding it (i.e., it represents a ``reflection'' along the ```
`   imaginary dimension).  Multiplying {{< math >}}c c^*{{< /math >}} gives the squared magnitude of`
`   the vector, which is a single real-valued scalar number.  It is the`
`   (squared) length of the hypotenuse of the vector.}`
` \label{fig.complex_numbers}`

\\end{figure}

We now introduce the symbol {{\< math \>}}\\phi{{\< /math \>}} (another
variant of the Greek symbol \`\`phi'', like {{\< math \>}}\\varphi{{\<
/math \>}}) to represent a complex-valued state variable:

-   {{\< math \>}}

` \phi & = & a + i b \non \\ & = & \varphi_a + i \varphi_b`
` \label{eq.cw_def}`

{{\< /math \>}} So, {{\< math \>}}\\phi{{\< /math \>}} is composed of
two separate real-valued numbers, designated {{\< math \>}}a{{\< /math
\>}} and {{\< math \>}}b{{\< /math \>}} (or {{\< math
\>}}\\varphi_a{{\< /math \>}} and {{\< math \>}}\\varphi_b{{\< /math
\>}}, to indicate that they are scalar state variables). A complex
number is really just a way of representing two separate real valued
numbers, aligned along orthogonal dimensions, in an efficient and
compact manner (Figure\~\\ref{fig.complex_numbers}). It is essential to
appreciate that, despite the presence of the imaginary number {{\< math
\>}}i{{\< /math \>}} (where {{\< math \>}}i^2 = -1{{\< /math \>}} or
{{\< math \>}}i = \\sqrt{-1}{{\< /math \>}}), {\\em all you ever really
have is two real-valued numbers}. There is nothing \`\`imaginary'' or
mysterious or spooky about the second number in a complex number: all
the {{\< math \>}}i{{\< /math \>}} does is keep these two values
separate from each other. In the end, we will deconstruct all of our
complex numbers into their real-valued components, and write purely
real-valued expressions that determine their update rules. These
expressions will be more complicated than the ones using complex
numbers, but they are required for actually implementing the equations
on the computer, and they also provide a more explicit and obvious
indication of exactly what drives each value.

Here's a few interesting facts about complex numbers: \\begin{itemize}
\\item To do algebra on them, you just have to remember to {\\em keep
the

`   real-values sorted separately from the imaginary ones}, but otherwise`
`   treat them just like a pair of numbers:`

-   {{\< math \>}}

`     y & = & a + ib \non \\ z & = & c + id \non \\ y + z & = & (a + c) + i(b`
`     + d) \non \\ y z & = & a c + i a d + i b c - b d \non \\ & = & (ac - bd)`
`     + i (ad + bc)`

{{\< /math \>}}

`   Notice that this multiplication rule is the same as {{< math >}}(a + b)(c + d) = ac +`
`   ad + bc + bd{{< /math >}}, where you just multiply everything through, except that you`
`   end up with these {{< math >}}i{{< /math >}} terms crossing over, and when you multiply {{< math >}}ib{{< /math >}} and`
`   {{< math >}}id{{< /math >}}, you end up with {{< math >}}i^2bd{{< /math >}}, at which point the {{< math >}}i^2{{< /math >}} disappears into a`
`   {{< math >}}-1{{< /math >}} (i.e., it crosses over from the imaginary world into the real one).`

`   As you should expect from Figure~\ref{fig.complex_numbers}, adding two`
`   complex numbers is like adding two vectors, and multiplication is just`
`   like multiplying vectors.  Complex numbers really are just a compact way`
`   of writing vectors!`

\\item Multiplication by {{\< math \>}}i{{\< /math \>}}: If you multiply
a complex number by {{\< math \>}}i{{\< /math \>}}, then you

` basically switch the real and imaginary parts: the real moves to the`
` imaginary position, and the imaginary becomes real:`

-   {{\< math \>}}

`   i(a + ib) = ia - b = -b + ia`

{{\< /math \>}}

` Geometrically, this is equivalent to rotating a vector by 90 degrees!  If`
` you do this four times, you'll end up back where you started (as you would`
` expect by doing a 360).`

\\item The complex conjugate of a complex number is just that number
with

` imaginary dimension inverted:`

-   {{\< math \>}}

`   y^* = a - i b`

{{\< /math \>}}

` The primary use of such a thing is to find the magnitude of a complex number`
` (i.e., the length of the vector that it represents), as:`

-   {{\< math \>}}

`   y y^* & = & (a + i b)(a - i b) \non \\ & = & a^2 - iab + iab + b^2 \non \\`
`   & = & a^2 + b^2`

{{\< /math \>}}

` This should be recognizable as simply the pythagorean theorem for the`
` squared length of the hypotenuse of a right triangle ({{< math >}}a^2 + b^2 = c^2{{< /math >}}).`
` Again, complex numbers have no mystery: they just represent a two-valued`
` vector.`

\\end{itemize}

\\subsubsection{Schrödinger's Equation}

Omitting various constants (factors of {{\< math \>}}h{{\< /math \>}})
and any external force potential, Schrödinger's equation is:

-   {{\< math \>}}

` i \frac{\partial {\phi}}{\partial t} = - \frac{1}{2m_0} \nabla^2 \phi`
` \label{eq.schrod_simple}`

{{\< /math \>}} where {{\< math \>}}m_0{{\< /math \>}} is again the
rest mass of the particle in question. This is clearly very similar to
the basic second-order KG wave equation (equation\~\\ref{eq.kg}):

-   {{\< math \>}}

` \frac{\partial^2 {\varphi}}{\partial t^2} = \nabla^2 \varphi - m_0^2 \varphi \non`

{{\< /math \>}} except that the temporal derivative is first-order, and
mass enters in a different way. Nevertheless, the \`\`driving force'' is
still the overall \`\`curvature'' of the wave, computed by {{\< math
\>}}\\nabla^2 \\varphi{{\< /math \>}}. As we noted above, the
multiplication by the {{\< math \>}}i{{\< /math \>}} term causes things
to rotate --- this rotation is key for making the first-order equation
behave like a wave.

To see this effect more explicitly, we can write out Schrödinger's
equation in terms of the two underlying scalar values:

-   {{\< math \>}}

` i \frac{\partial {\varphi_a + i \varphi_b}}{\partial t} & = & - \frac{1}{2m_0} \nabla^2 (\varphi_a + i \varphi_b) \non \\`
` -\frac{\partial {\varphi_b}}{\partial t} + \frac{\partial {i \varphi_a}}{\partial t} & = & -\frac{1}{2m_0} \nabla^2 \varphi_a - i \nabla^2 \varphi_b`

{{\< /math \>}} where {{\< math \>}}\\varphi_a{{\< /math \>}} indicates
a scalar state variable that is the {{\< math \>}}a{{\< /math \>}}
component of {{\< math \>}}\\phi{{\< /math \>}}, and {{\< math
\>}}\\varphi_b{{\< /math \>}} is the {{\< math \>}}b{{\< /math \>}}
component of {{\< math \>}}\\phi{{\< /math \>}}. Note that the
derivatives operate separately on each of the two variables. At this
point, we now can just separate all the terms that involve an {{\< math
\>}}i{{\< /math \>}} from those that do not, to get update equations for
each of the two variables. For the real-valued components (without the
{{\< math \>}}i{{\< /math \>}}):

-   {{\< math \>}}

` -\frac{\partial {\varphi_b}}{\partial t} & = & - \frac{1}{2m_0} \nabla^2 \varphi_a \non \\ \frac{\partial {\varphi_b}}{\partial t} & = &`
` \frac{1}{2m_0} \nabla^2 \varphi_a`
` \label{eq.schrod_b}`

{{\< /math \>}} and for the imaginary components (dropping the {{\< math
\>}}i{{\< /math \>}} now, because we no longer need it to keep the
variables separated):

-   {{\< math \>}}

` \frac{\partial {\varphi_a}}{\partial t} & = & - \frac{1}{2m_0} \nabla^2 \varphi_b`
` \label{eq.schrod_a}`

{{\< /math \>}}

In a discrete-space and time CA-like implementation, these equations
would be written:

-   {{\< math \>}}

` \dot \varphi_a_i^{t+1} & = & - \frac{3}{26 m_0}\sum_{j \in {\cal N}_{26}} k_j`
` (\varphi_b_j^t - \varphi_b_i^t) \non \\ \varphi_a_i^{t+1} & = & \varphi_a_i^t + \dot`
` \varphi_a_i^{t+1}`
` \label{eq.disc_schrod_a}`

{{\< /math \>}} and:

-   {{\< math \>}}

` \dot \varphi_b_i^{t+1} & = & \frac{3}{26 m_0}\sum_{j \in {\cal N}_{26}} k_j`
` (\varphi_a_j^t - \varphi_a_i^t) \non \\ \varphi_b_i^{t+1} & = & \varphi_b_i^t + \dot`
` \varphi_b_i^{t+1}`
` \label{eq.disc_schrod_b}`

{{\< /math \>}}

So, in the end, Schrödinger's equation really just boils down to two
very simple differential equations. Interestingly, these equations are
\`\`coupled*, in the sense that it is the curvature of {{\< math
\>}}\\varphi_a{{\< /math \>}} that drives the change in {{\< math
\>}}\\varphi_b{{\< /math \>}}, and vice-versa. This is the
\`\`rotational* aspect of the equation mentioned earlier, which is
caused by the presence of the {{\< math \>}}i{{\< /math \>}} in the
equation.

For completeness, the full version of Schrödinger's equation is:

-   {{\< math \>}}

` i \hbar \frac{\partial {\phi}}{\partial t} = -\frac{\hbar^2}{2m_0} \nabla^2 \phi + V \phi`
` \label{eq.schrod_full}`

{{\< /math \>}} where {{\< math \>}}\\hbar = \\frac{h}{2\\pi}{{\< /math
\>}} and {{\< math \>}}V{{\< /math \>}} is a scalar \`\`energy
potential'' that imparts some measure of force on the particle (it is
essentially the electrical potential).

When you actually implement Schrödinger's equation on a computer using
the update rules given above (equations\~\\ref{eq.disc_schrod_a} and
\\ref{eq.disc_schrod_b}), the resulting system is numerically
unstable. In other words, the resulting numbers quickly blow up to
infinity. This is not due to any kind of numerical roundoff error from
limited precision floating point numbers on the computer, but rather due
to the way that changes in state values reverberate back and forth
across the two scalar values. However, it is possible to overcome it
relatively simply by just alternating the update: on one time step you
compute one value (equation\~\\ref{eq.disc_schrod_a}), and on the next
you update the other (equation\~\\ref{eq.disc_schrod_b}). This is what
is done for illustrative purposes in the computer explorations. The
basic phenomenology of Schrödinger's equation is that wave packets
propagate through space, with a speed that is proportional to {{\< math
\>}}\\nabla^2 \\phi{{\< /math \>}}, which in turn is proportional to the
frequency of the wave. In other words, it describes exactly the same
behavior as the KG equation, where particle speed is proportional to
frequency.

One critical property of Schrödinger's equation (which our current
scalar KG equation does not have) is that it preserves the overall
magnitude of the {{\< math \>}}\\phi{{\< /math \>}} state values across
all of space, for all time. This is to say, if you compute the sum of
{{\< math \>}}\\phi \\phi^\*{{\< /math \>}} for each point in space,
this sum will remain the same across time under the Schrödinger
equation. This conserved value is interpreted as a probability in
standard quantum mechanics. For example, we can initialize the state
with a localized wave packet (Figure\~\\ref{fig.wave_packet}) to
represent the initial probability for the location and velocity of a
particle (velocity being a function of the frequency of the wave
packet). If we then apply the Schrödinger equation repeatedly, we can
interpret the resulting {{\< math \>}}\\phi \\phi^\*{{\< /math \>}}
values as the probability of the particle having moved to the
corresponding location.

In other words, the wave packet defines a kind of \`\`cloud of
probability'' for finding a discrete particle within its midst. However,
these probabilities have different meanings in different scenarios, and
it is notoriously difficult to come up with a intuitively sensible
interpretation of what these probability clouds mean. We return to these
issues later.

% todo: demos of schrodinger..

\\subsection{Energy and Momentum Operators}

The KG and Schrödinger wave equations can also be derived in a more
\`\`top-down'' manner, compared to the very \`\`bottom-up'' mechanistic
considerations we have explored thus far. This top-down perspective has
to do with the relationships between energy and momentum that hold for
basic Newtonian physics. Specifically, one can define something called
the {\\em Hamiltonian} ({{\< math \>}}H{{\< /math \>}}), which is the
total energy of the system. This total energy is strictly conserved over
time, and one can derive Newton's laws of motion from this basic fact
--- things can move this energy around in different ways, but they
cannot change the total amount.

For a single particle moving in the presence of a potential energy
function {{\< math \>}}V{{\< /math \>}}, the total energy of the system
is equal to the kinetic energy {{\< math \>}}K{{\< /math \>}} of the
particle plus this potential energy:

-   {{\< math \>}}

` H & = & K + V \non \\ & = & \frac{1}{2 m_0} \vec{p}^2 + V`
` \label{eq.hamiltonian}`

{{\< /math \>}} This way of expressing the kinetic energy {{\< math
\>}}K{{\< /math \>}} in terms of momentum {{\< math \>}}\\vec{p}{{\<
/math \>}} is important for the next steps. It can be derived very
directly from the perhaps more familiar definition of kinetic energy in
terms of velocity {{\< math \>}}\\vec{v}{{\< /math \>}} squared:

-   {{\< math \>}}

` K = \frac{1}{2} m_0 \vec{v}^2`

{{\< /math \>}} First, we express velocity in terms of momentum:

-   {{\< math \>}}

` \vec{p} & = & m_0 \vec{v} \non \\ \vec{v} & = & \frac{1}{m_0} \vec{p}`

{{\< /math \>}} and just substitute this into the above kinetic energy
equation:

-   {{\< math \>}}

` K & = & \frac{1}{2} m_0 \vec{v}^2 \non \\ & = & \frac{1}{2} m_0 \frac{1}{m_0^2}`
` \vec{p}^2 \non \\ & = & \frac{1}{2 m_0} \vec{p}^2`

{{\< /math \>}}

Interestingly, Schrödinger's equation can be derived by using the
Hamiltonian equation (\\ref{eq.hamiltonian}) together with energy and
momentum operators that apply to wave functions (e.g., {{\< math
\>}}\\phi{{\< /math \>}}). Intuitively, energy is associated with
changes over time, and momentum with changes over space. Thus, the total
energy of a wave is proportional to its first temporal derivative:

-   {{\< math \>}}

` E \propto \frac{\partial {\phi}}{\partial t}`

{{\< /math \>}} and the momentum is proportional to its first spatial
derivative:

-   {{\< math \>}}

` \vec{p} \propto \vec{\nabla} \phi`

{{\< /math \>}} (where {{\< math \>}}\\vec{\\nabla} =
\\left(\\frac{\\partial {}}{\\partial {x}}, \\frac{\\partial
{}}{\\partial {y}}, \\frac{\\partial {}}{\\partial {z}}\\right){{\<
/math \>}}). So if you just take these formulas and plug them into the
Hamiltonian equation (where we substitute E for the total energy H), you
get:

-   {{\< math \>}}

` E & = & \frac{1}{2 m_0} \vec{p}^2 + V \non \\ \frac{\partial {\phi}}{\partial t} & = & \frac{1}{2 m_0}`
` \nabla^2 \phi + V \phi`

{{\< /math \>}} (where the laplacian {{\< math \>}}\\nabla^2 =
\\vec{\\nabla}^2{{\< /math \>}}). This is basically Schrödinger's
equation, just missing the factors of {{\< math \>}}i \\hbar{{\< /math
\>}}. These factors are in fact the missing constants in the energy and
momentum equations, which are properly written in \`\`operator form''
(i.e., as things that operate on a wave function to return the
associated energy or momentum value), as:

-   {{\< math \>}}

` \hat{E} & = & i \hbar \frac{\partial {}}{\partial t} \non \\ \hat{p} & = & -i \hbar \vec{\nabla}`
` \label{eq.ep_operators}`

{{\< /math \>}} where the little \`\`hats'' {{\< math \>}}\\hat{\\;}{{\<
/math \>}} indicate that these are operators. I have no idea how to
independently motivate these {{\< math \>}}i \\hbar{{\< /math \>}}
factors, but in any case, they are just constants so it is not all that
important. If we use these for the Hamiltonian, we recover the full
Schrödinger equation:

-   {{\< math \>}}

` E & = & \frac{1}{2 m_0} \vec{p}^2 + V \non \\ i \hbar \frac{\partial {\phi}}{\partial t} & = & -`
` \frac{\hbar^2}{2 m_0} \nabla^2 \phi + V \phi`

{{\< /math \>}}

The net result is that we can conclude that Schrödinger's equation
provides an accurate description of the flow of energy and momentum over
time of a \`\`particle'' described by a wave, such that it obeys
classical Newtonian physical laws.

The reason that Schrödinger's equation is not correct from the
perspective of special relativity, and the KG equation is, can be
derived from the definition of total energy in the system. The above
definition, from which Schrödinger's equation follows, is for a
classical Newtonian system. For a relativistic system, the proper
definition of total energy was given in equation\~\\ref{eq.rel_e} (note
that this does not include any potential energy):

-   {{\< math \>}}

` E^2 & = & \vec{p}^2 c^2 + (m_0 c^2)^2 \non \\ E & = & \sqrt{\vec{p}^2 c^2 +`
` (m_0 c^2)^2}`

{{\< /math \>}} If you use this new expression as the basis for a
Hamiltonian for a wave equation, using the same energy and momentum wave
operators, you end up with this:

-   {{\< math \>}}

` E & = & \sqrt{\vec{p}^2 c^2 + (m_0 c^2)^2} \non \\ i \hbar \frac{\partial {\phi}}{\partial t} & = &`
` \left( \sqrt{-\hbar^2 \nabla^2 c^2 + (m_0 c^2)^2} \right) \phi`

{{\< /math \>}} which doesn't really compute all that well, for several
reasons (it is non-local because of the square root of the laplacian,
and it is not obviously relativistic either because time and space are
not treated equally; see \\incite{Gingrich04} for more discussion).

However, you can instead use the squared energy form of this expression,
and then substitute in the energy and momentum operators:

-   {{\< math \>}}

` E^2 & = & \vec{p}^2 c^2 + (m_0 c^2)^2 \non \\ - \hbar^2 \frac{\partial^2 {\phi}}{\partial t^2} & = &`
` \left (-\hbar^2 \nabla^2 c^2 + (m_0 c^2)^2 \right) \phi \non \\ \frac{\partial^2 {\phi}}{\partial t^2} & =`
` & \left( c^2 \nabla^2 - \frac{(m_0 c^2)^2}{\hbar^2} \right) \phi \non \\`
` \frac{\partial^2 {\phi}}{\partial t^2} & = & c^2 \left(\nabla^2 - \frac{m_0^2 c^2}{\hbar^2}\right) \phi`

{{\< /math \>}} In natural units where {{\< math \>}}c = \\hbar = 1{{\<
/math \>}}, this is our favorite KG equation:

-   {{\< math \>}}

` \frac{\partial^2 {\phi}}{\partial t^2} = \left(\nabla^2 - m_0^2\right) \phi`

{{\< /math \>}}

This exercise in mathematics provides a concise derivation of the fact
that the KG equation is a relativistic version of Schrödinger's
equation, and that it encompasses all of special relativity, which in
turn includes classical Newtonian mechanics as a special case when
velocities are small relative to the speed of light. These are pretty
powerful statements, and in general that is the benefit of using the
energy-momentum analysis --- it is more abstract, but also more
all-encompassing in scope.

\\subsubsection{Four-Vector Version}

Before continuing, we explore the ultra-compact version of the above
derivations that is possible using the four-vector space-time coordinate
system introduced earlier. In this system, the {\\em four-momentum}
operator is defined as:

-   {{\< math \>}}

` {\hat{p}^\mu} & = & i \hbar \partial^\mu \non \\ & = & i \hbar`
` \left(\frac{\partial {}}{\partial {ct}},-\frac{\partial {}}{\partial {x}},-\frac{\partial {}}{\partial {y}},- \frac{\partial {}}{\partial {z}}\right) \non \\ & = & i \hbar`
` \left(\frac{\partial {}}{\partial {ct}}, -\vec{\nabla} \right) \non \\ & = & \left(\frac{\hat{E}}{c},`
` \hat{p}\right)`
` \label{eq.4p}`

{{\< /math \>}} As indicated, it should be clear that the first (time)
component of this is the energy operator given above, while the spatial
components are the momentum operator
(equation\~\\ref{eq.ep_operators}):

-   {{\< math \>}}

` \hat{E} & = & i \hbar \frac{\partial {}}{\partial t} \non \\ \hat{p} & = & -i \hbar \vec{\nabla}`

{{\< /math \>}} If you then square this momentum operator (using the
standard covariant, contravariant four-vector definition of multiplying
vectors), you get:

-   {{\< math \>}}

` {\hat{p}^\mu} {\hat{p}_\mu} = \frac{\hat{E}^2}{c^2} - \hat{p}^2`

{{\< /math \>}} Now this is quite interesting, because it can be
directly related to the relativistic energy-momentum equation:

-   {{\< math \>}}

` E^2 & = & \vec{p}^2 c^2 + (m_0 c^2)^2 \non \\ \frac{E^2}{c^2} & = &`
` \vec{p}^2 + m_0^2 c^2 \non \\ \frac{E^2}{c^2} - \vec{p}^2 & = & m_0^2 c^2`

{{\< /math \>}} So we can now put these two equations together, to get:

-   {{\< math \>}}

` {\hat{p}^\mu} {\hat{p}_\mu} = m_0^2 c^2`

{{\< /math \>}} Now, we also know that the wave equation arises from the
second-order derivatives of a four-vector
(equation\~\\ref{eq.covgrcongr}):

-   {{\< math \>}}

` \partial_\mu \partial^\mu = \frac{1}{c^2}\frac{\partial^2 {}}{\partial t^2} - \nabla^2`

{{\< /math \>}} and this four-momentum operator is essentially just a
first-order derivative with some additional constants (including the
{{\< math \>}}i{{\< /math \>}} term, which, when squared produces a {{\<
math \>}}-1{{\< /math \>}}), so when we apply these operators to our
wave variable {{\< math \>}}\\phi{{\< /math \>}}, we get:

-   {{\< math \>}}

` {\hat{p}^\mu} {\hat{p}_\mu} \phi & = & m_0^2 c^2 \phi \non \\ i^2 \hbar^2`
` \partial_\mu \partial^\mu \phi & = & m_0^2 c^2 \phi \non \\ - \hbar^2`
` \left(\frac{1}{c^2}\frac{\partial^2 {}}{\partial t^2} - \nabla^2\right) \phi & = & m_0^2 c^2 \phi \non \\`
` \frac{\partial^2 {\phi}}{\partial t^2} & = & c^2 \left(\nabla^2 - \frac{m_0^2c^2}{\hbar^2}\right) \phi \non`
` \\`

{{\< /math \>}} Which is right back to our KG wave equation.

In summary, the core of the KG wave equation, and of special relativity,
and much of quantum mechanics, can all be reduced to this one simple
equation:

-   {{\< math \>}}

` \boxed{{\hat{p}^\mu} {\hat{p}_\mu} \phi = m_0^2 c^2 \phi}`
` \label{eq.kg_p4v}`

{{\< /math \>}} This is in some sense the most fundamental equation of
the universe, subsuming the more popular {{\< math \>}}E = m c^2{{\<
/math \>}} and, as we'll see, providing the basis for further extensions
to the KG equation.

\\subsection{Vista Point 2}

To summarize our progress so far, we have seen that in the domain of
forces, the electromagnetic field can be understood in terms of four
wave equations operating in parallel, driven by the charge density and
charge current density. In the domain of matter, the Klein-Gordon wave
equation allows us to describe particles having the following
properties: \\begin{itemize} \\item Motion at continuously variable
speeds, in all directions (without asymmetries caused by the underlying
grid matrix). \\item Newtonian (classical) physics (law of inertia, law
of force) (in the limit of small velocities relative to the speed of
light). This means that our model can explain virtually all of the
intuitive everyday phenomena of physics (e.g., billiard balls and cars
moving and everything that doesn't require gravity to explain). \\item
Many aspects of quantum mechanics (e.g., momentum proportional to wave
frequency), by virtue of the KG equation being the relativistic version
of Schrödinger's equation. \\item Special relativity (Lorentz
contraction, time dilation, mass inflation), which can be understood
mechanistically in terms of the properties of KG waves as they move at
increasingly faster speeds (higher frequency = shorter wavelength =
space contraction, etc), and abstractly in terms of the KG equation
satisfying the relativistic energy Hamiltonian. \\end{itemize}

Again, we see that an astounding swath of fundamental physics emerges
from an exceedingly simple system, which is very nearly the simplest
version of a continuous cellular automaton that does anything
interesting at all. We simply added one additional term to the basic
wave equation (the \`\`mass drag'' term), and from that follows so many
central features of our reality. Again, one is left with the strong
feeling that there must be something to this: the ratio of important
stuff explained to assumptions made is exceedingly high.

This ratio is critical. You can think of it as \`\`bang for the buck'',
and scientists are extremely frugal shoppers, in these terms.
Assumptions are costly, and the fewer of them you can make to explain
the same amount of stuff, the better. Here, we have made an extremely
small set of basic, strongly-motivated assumptions, and wound up with
almost every major feature of known physics! The most important missing
part is gravitation, but we'll get to that later.

Interestingly, this is somewhat of a high-water mark in this respect, in
that the subsequent developments of our model will largely result in
increases in complexity that produce apparently relatively minor
additional explanatory benefit. However, there is good reason to believe
that many of the complex and beautiful phenomena of our universe could
not exist without these extra degrees of complexity: the basic EM wave
and KG equations do a huge amount, and are a very solid foundation, but
they fall short of capturing important things like charge, and the
interaction between charges via the electromagnetic field. As they say,
the devil is in the details, and our current model is just a bit to
smooth and simple to provide sufficiently complex dynamics to support
beings like us, to sit here and ponder it all. In any case, the other
thing scientists care a lot about is actually explaining the known data,
and without these extra additions, the model simply does not.

Another important milestone that we've reached here is the contemplation
of what it would require to have discrete particles in our system. They
just do not work. In contrast to our wave equations, particles introduce
massive amounts of complexity without adding much of any unexpected
benefits. Therefore, we are entirely prepared at this point to discard
the notion of a discrete particle entirely. The implications of such a
move will reverberate throughout the rest of the paper.

Overall, it is interesting to compare our strong enthusiasm for the KG
equation with its almost total neglect in the physics literature, which
instead has been dominated by Schrödinger's equation and the Dirac
equation that we'll encounter later. We like the KG equation because it
is extremely simple and elegant from the perspective of our cellular
automaton model, and its second-order nature both emerges naturally out
of this framework, and solves a number of important problems (e.g.,
symmetric propagation in all directions, which does not occur in a
first-order wave equation in the CA framework). In contrast, the rest of
physics likes Schrödinger's equation because it is more analytically
tractable as a first-order equation. It is linear, and it also
automatically produces a positive-valued conserved probability density,
which fits perfectly with the standard probabilistic interpretation of
quantum physics. The fact that it violates special relativity is often
overlooked, and anyway the Dirac equation solves that problem, while
staying within a first-order framework (but at the cost of introducing 8
state variables interacting in a fairly complex way). Thus, the overall
difference is one of \`\`mechanism'' vs. \`\`analysis,'' where standard
physics is strongly weighted toward analysis. Nevertheless, we'll see
that with appropriate further developments, a version of the KG equation
can provide a correct explanation of all the phenomena covered by the
Dirac equation.