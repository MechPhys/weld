---
title: "WELDBook Waves"
---

Back to [Main Page](/WELDBook/Main "wikilink")

Waves are the foundation of the wave electrodynamics (WELD) model, so we
start here by exploring the basic properties of the simplest kind of
waves, produced by a **second-order wave equation**. This is an
idealization of the kinds of waves that are familiar to you in everyday
life: water waves, sound waves, guitar strings and drum surfaces
vibrating, etc. There are a few key physical properties of these systems
that produce wave behavior:

-   Stuff in one location can move in some way relative to stuff in
    neighboring locations, creating a **disturbance**: water molecules,
    guitar string, and drum skin can move up and down.
-   When stuff in one location does move relative to its neighbors, it
    experiences a **restoring force** pulling it back in line with the
    neighbors.
-   The stuff also has **inertia** that keeps it moving *past* the point
    of equality with the neighbors, creating a new disturbance in the
    opposite direction, which is then subject to a new restoring force,
    causing the process to repeat again.

We can capture these properties in a simple linear equation, which
constitutes the standard second-order wave equation. It is "second
order" in order to capture the inertia property.

Aside from looking completely mesmerizing, these simple waves can
exhibit some important properties. At the most basic level, we can
measure things like **frequency**, **wavelength**, and **phase** of the
wave vibrations. And critically for understanding quantum mechanics,
waves exhibit the amazing property of **superposition** -- two different
waves can pass right through each other and come out the other side
unscathed, due to the linearity of the wave equation. This ability to
encode many different things all added up together into one complex wave
disturbance is leveraged in QM to capture a combination of different
uncertain possibilities all wrapped up in one inscrutable package.

# The Wave Equation

TODO: discrete 1d wave equation figure.

We start by deriving the basic second order wave equation, in a simple
one-dimensional case with discrete uniform cells each having a "state
value" that represents the "stuff" that moves around in the wave (e.g.,
the height of water) (). In a simple computer program, the wave equation
is:

    neigh_avg = .5 * (neigh_l + neigh_r)      // average of my neighbor values
    force = neigh_avg - prv;   // force acting on me = neighbors vs. my previous value (prv)
    acc = c_sq * force;            // acceleration = force, and speed of light acts as a kind of mass-like term in f=ma; a = f/m
    newvel = vel + acc;           // new velocity = previous velocity + new acceleration
    val = prv + newvel;           // new value = previous value + new velocity