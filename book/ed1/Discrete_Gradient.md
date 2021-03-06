---
title: "WELDBook Discrete Gradient"
---

To compute the vector gradient in our discrete space-time cellular
automaton, we need to introduce a new fundamental computation over the
neighbors (all the previous equations have all just involved a single
neighborhood computation for the Laplacian {{\< math \>}}\\nabla^2{{\<
/math \>}}). This is one sense in which the model starts getting a bit
more complex (it turns out that this computation will also be needed
later for coupling with the electromagnetic field as well). First, in a
single spatial dimension for state variable {{\< math \>}}s{{\< /math
\>}}, we saw before (equation\~\\ref{eq.diff_avg}) that the
differential can be approximated as:

-   {{\< math \>}} \\frac{\\partial {s}}{\\partial {x}} \\approx
    \\frac{1}{2 \\epsilon} (s_{i+1} - s_{i-1}) {{\< /math \>}}

\\begin{figure}

` \centering\includegraphics[height=1.5in]{fig.space_cubes_grad_noleg.id}`
` \caption{\small Computation of the spatial gradient using all 18`
`   neighbors that have a non-zero projection along a given axis (in this`
`   case, looking at the x axis).  The two face points ({{< math >}}+,-{{< /math >}} along the axis)`
`   have a full projection along the axis, and thus enter with a weight of 1.`
`   The 8 edge points each have a {{< math >}}\frac{1}{\sqrt{2}}{{< /math >}} projection of their`
`   overall distance along the axis, and thus contribute with that overall`
`   weighting.  Similarly, the 8 corners have a {{< math >}}\frac{1}{\sqrt{3}}{{< /math >}} projection`
`   weighting.  In computing the weighted average, the sum of all neighbor`
`   differences is divided by the sum of the weighting terms.}`
` \label{fig.grad}`

\\end{figure}

In three dimensions, the computation can be made more accurate and
robust by including more of the neighbors, just as we did for the
computation of {{\< math \>}}\\nabla^2{{\< /math \>}}. The most relevant
neighbors are the 18 that have some projection along an axis, as
illustrated in Figure\~\\ref{fig.grad}. These can be organized into 9
rays that project through the central point, so that the above
approximation can be extended to:

-   {{\< math \>}} \\frac{1}{(2 + \\frac{8}{\\sqrt{2}} +
    \\frac{8}{\\sqrt{3}})} \\sum_{j \\in N_{9}} k_j (\\varphi_{j+} -
    \\varphi_{j-}) {{\< /math \>}}

Where the neighborhood {{\< math \>}}N_{9}{{\< /math \>}} contains
pairs of points {{\< math \>}}j+{{\< /math \>}} and {{\< math \>}}j-{{\<
/math \>}} that are opposite ends of the 9 rays through the central
point, and the distance weighting factors {{\< math \>}}k_j{{\< /math
\>}} are:

-   **faces:** {{\< math \>}} k_j = \\pm 1 {{\< /math \>}}
-   **edges:** {{\< math \>}} k_j = \\pm \\frac{1}{\\sqrt{2}} {{\<
    /math \>}}
-   **corners:** {{\< math \>}} k_j = \\pm \\frac{1}{\\sqrt{3}} {{\<
    /math \>}}