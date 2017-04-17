title: Geometry Processing Course
author: Klint Qinami, Alec Jacobson
html header:  <link rel="stylesheet" href=style.css>

# Geometry Processing

![](images/libigl-teaser.jpg)

Winter Term 2017  
CSC2521 [Topics in Computer Graphics: Geometry Processing]  
Prof. Alec Jacobson  
W 3-5 BA 5187 (via BA 5166)  

The class is aimed at preparing students for working with geometric data via
understanding fundamental theoretical concepts. Students should have a
background in _Linear Algebra_ and _Computer Programming_. Previous
experience with _Numerical Methods_, _Differential Equations_, and _Differential
Geometry_ is appreciated but not required.

Extending traditional signal processing, _geometry processing_ interprets
three-dimensional curves and surfaces as signals. Just as audio and image
signal data can be filtered, denoised and decomposed spectrally, so can the
geometry of a three-dimensional curve or surface.

In this course, we study the algorithms and mathematics behind fundamental
operations for interpreting and manipulating geometric data. These essential
tools enable: geometric modeling for computer aided design, life-like
animations for computer graphics, reliable physical simulations,  and robust
scene representations for computer vision.

Topics include: discrete curves and surfaces, curvature computation, surface
reconstruction from point clouds, surface smoothing and denoising, mesh
simplification, parameterization, symmetry detection, shape deformation and
animation.


## Organization

In lecture we will cover the mathematical background and visual intuition of
the week's topic. At home, students will **_read academic papers_** and complete a
small **_weekly_** programming assignment to implement a corresponding
algorithm. By the end of the semester, these algorithms compose a toolbox that
students can use to create a unique _artifact_: the **_final project_** is to
use these tools to create a unique piece of geometry to visualize (as an image
or interactive experience) or 3D print. 

## Objectives

 1. Students should understand, derive, and implement solutions to the
 prominent challenges that arise in geometry processing applications.
 2. Students should create a final creative project showcasing their
 implementation of the different processing algorithms.
 3. Students should develop an understanding of the mathematical underpinnings
 of geometry processing including useful discretized operators and energies.
 4. Students should develop a working knowledge of
 [libigl](http://libigl.github.io/libigl/) to develop these algorithms without
 worrying about the grunt-work of
 [OpenGL](https://en.wikipedia.org/wiki/OpenGL) viewers, quadrature, etc.

## Prerequisites

Students should have already taken **Linear Algebra** and **Calculus**.

Students should have already taken **Introduction to Computer Science** and
should be _proficient_ in computer programming (in any language) and should
feel comfortable programming in **C++**.

While knowledge of **Partial Differential Equations** _is not required_, it will
certainly be very handy for derivations. A quick survey will be posted to help
students evaluate their readiness on these topics.

On the programming side, we will be coding mainly in **C++** and using a
[libigl](http://libigl.github.io/libigl/), an open-source geometry processing
library. We will be using [Eigen](http://eigen.tuxfamily.org) for computational
linear algebra, and [Cmake](http://cmake.org) for building the coding
assignments.

## A Mathematical Foundation

Much of the framing for our techniques will be looking at the continuous
analogue of our problem and discretizing it in an intrinsic way, preserving
continuous theorems as much as possible. We will discretize continuous
operators like the Laplacian and the Gradient, and we will find adequate
representations of concepts like normal vectors and curvature. Perhaps
surprisingly we will see that there are many choices of discretization, each
with their own benefits and downsides, prompting us to choose appropriately for
the particular application.

## Schedule

| Lecture Date          | Tentative Topic |
|:----------------------|:--|
| Wednesday, 11/01/2017 | [**Geometry Processing Pipeline**](lecture-notes/introduction.html), shapes, surface representations, tangents and normals, <del>data structures, linear algebra</del>, topology, libigl. <br> _Polygon Mesh Processing_ [Botsch et al. 2008] <br> _**[HW 00 assigned](https://github.com/alecjacobson/geometry-processing-introduction), due 17/01/2017**_
| Wednesday, 18/01/2017 | [**Acquisition & reconstruction**](lecture-notes/mesh-reconstruction.html), discrete topology, meshes, characteristic function, scattered data interpolation, spatial gradient, <del>spatial Laplacian</del>, linear least squares, <br> "Poisson surface reconstruction" [Kazhdan et al. 2006] <br> _**[HW 01 assigned](https://github.com/alecjacobson/geometry-processing-mesh-reconstruction) due 29/01/2017**_
| Wednesday, 25/01/2017 | [**Alignment & registration**](lecture-notes/registration.html) Hausdorff distance, point-to-plane distance, iterative closest point, orthogonal Procrustes problem, sampling points on surfaces <br> "Object modelling by registration of multiple range images" [Chen & Medioni 1991] <br> "A method for registration of 3-D shapes" [Besl & McKay 1992] <br> "Efficient Variants of the ICP Algorithm" [Rusinkiewicz & Levoy 2001] <br> "Sparse Iterative Closest Point" [Bouaziz et al. 2013] <br> _**[HW 02 assigned](https://github.com/alecjacobson/geometry-processing-registration) due 5/2/2017**_ |
| Wednesday, 01/02/2017 | [_Alignment & registration continued_](lecture-notes/registration.html), [**Surface fairing & denoising**](lecture-notes/smoothing.html), 1D smoothing flow, 1D energy-based smoothing, PDE, Implicit Time integration<br> [Discrete Differential Geometry "Forum"](http://ddg.cs.columbia.edu)<br> "Curve and surface smoothing without shrinkage" [Taubin 1995] <br> "Skeleton extraction by mesh contraction" [Au et al. 2008]<br> "Can Mean-Curvature Flow Be Made Non-Singular" [Kazhdan et al. 2005]<br>_**[HW 03 assigned](https://github.com/alecjacobson/geometry-processing-smoothing) due 13/2/2016**_|
| Wednesday, 08/02/2017 | [**Surface parameterization**](lecture-notes/parameterization-ryan-schmidt.pdf), Guest lecture by [Ryan Schmidt](http://www.rms80.com), texture mapping, mass-spring methods, graph drawing, harmonic maps, least squares conformal mapping, local parameterization, discrete exponential map, stroke parameterization <br> "Intrinsic parameterizations of surface meshes" [Desbrun et al. 2002] <br> "Least squares conformal maps for automatic texture atlas generation" [Lévy et al. 2002] <br> "Spectral conformal parameterization" [Mullen et al. 2008] |
| Wednesday, 15/02/2017 | [_Smoothing continued_](lecture-notes/smoothing.html), Spatial Laplacian, calculus of variations, Green's Identity _**[HW 04 assigned](https://github.com/alecjacobson/geometry-processing-parameterization), due 28/2/2017**_
| Wednesday, 22/02/2017 | _Retroactively decided that this is Reading Week_, <br> [_Surface parameterization continued_](lecture-notes/parameterization-ryan-schmidt.pdf), role of trace in quadratic energies, minimizing quadratic energies in libigl |
| Wednesday, 01/03/2017 | [**Shape deformation**](lecture-notes/deformation.html), continuous deformation, pointwise mappings, energy-based model, handle-based deformation, local distortion mesure, gradient-based distortion, Laplacian-based distortion, as-rigid-as-possible <br> "An intuitive framework for real-time freeform modeling" [Botsch & Kobbelt 2004] <br> "On linear variational surface deformation methods" [Botsch & Sorkine 2008] <br> "As-rigid-as-possible surface modeling" [Sorkine & Alexa 2007] <br> "Bounded Biharmonic Weights for Real-Time Deformation" [Jacobson et al. 2010] _**[HW 05 assigned](https://github.com/alecjacobson/geometry-processing-deformation) due 12/3/2017**_|
| Wednesday, 08/03/2017 | [**Curvature & surface analysis**](lecture-notes/curvature.html) Planar curves, tangents, arc-length parameterization, osculating circle, curvature, turning number theorem, discrete curvature, normal curvature, minimum/maximum/mean curvature <br> _Elementary Differential Geometry_, [Barret O'Neill 1966  <br> _Discrete Differential Geometry: An Applied Introduction_, SIGGRAPH Course, [Grinspun et al. 2005] |
| Wednesday, 15/03/2017 | [_Curvature continued_](lecture-notes/curvature.html) Principal curvature, Gauss map, Euler's theorem, shape operator, Gaussian curvature <br> "Computing Discrete Minimal Surfaces and Their Conjugates" [Pinkall and Polthier 1993] <br> "Gaussian Curvature and Shell Structures" [Calladine 1986] <br> "Discrete differential-geometry operators for triangulated 2-manifolds" [Meyer et al. 2002] <br> _**[HW 06 assigned](https://github.com/alecjacobson/geometry-processing-curvature), due 22/3/2017**_
| Wednesday, 22/03/2017 | [**Moment integration**](lecture-notes/moment-nobuyuki-umetani.pdf), guest lecture by [Nobuyuki Umetani](http://nobuyuki-umetani.com) <br> 3D printing, density, mass, center of mass, moment of inertia, divergence theorem, simplex integration, balance. |
| Wednesday, 29/03/2017 | [**Signed distances**](lecture-notes/signed-distance.html), Offset surfaces, inside-outside segmentation, medial axis, isosurface/level sets, signed distances to polyhedra, parity counting, winding number <br> "Signed Distance Computation using the Angle Weighted Pseudo-normal" [Baerentzen & Aanaes 2005] <br> "3D distance fields: a survey of techniques and applications" [Jones et al. 2006] <br> "Robust Inside-Outside Segmentation using Generalized Winding Numbers" [Jacobson et al. 2013] [ 
| Wednesday, 05/04/2017 | **Final project presentations** |

> Cutting room floor: **Mesh decimation, simplification, remeshing**,  **Quad
> meshing**, **Subdivision surfaces**, **Constructive solid geometry**,
> **Voxelization**

## Lateness Policy

0.007% off for every minute late.

## Supplemental Textbook

[_Polygon Mesh
Processing_](https://www.amazon.ca/Polygon-Mesh-Processing-Mario-Botsch/dp/1568814267/).
Mario Botsch, Leif Kobbelt, Mark Pauly, Pierre Alliez, and Bruno Levy, 2008.

## Grading

- 50% small assignments
- 25% final project: 
    - in-class presentation
    - formal two-page [technical extended
      abstract](http://s2017.siggraph.org/talks-submissions)
    - (less formal) in depth documentation
    - it's great if you can align with your research, but please discuss this
      with me early on.
- 20% participation: in class, reading papers, answering "Issues" on
  assignments
- 5% full-class collaborative project: improve
  [https://en.wikipedia.org/wiki/Geometry_processing](https://en.wikipedia.org/wiki/Geometry_processing)
  and [related
  topics](https://en.wikipedia.org/wiki/Category:Geometry_processing)
    - Graded based on delta of this page between now and end of term
    - Grade is shared by entire class

