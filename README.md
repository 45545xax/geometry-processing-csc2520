# Geometry Processing

[Register your email address for the class](https://goo.gl/forms/5d1luoU2QPlPky0h2)

![](images/libigl-teaser.jpg)

Fall Term 2018  
CSC2520H Geometry Processing  
CSC490H1 Capstone Design: Geometry Processing  
Prof. Alec Jacobson  
TA, Michael Tao  
T 3-5 MP 137  

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
| Tuesday, 11/09/2018 | [**Geometry Processing Pipeline**](lecture-notes/introduction.md), "life of a shape", shapes, surface representations, <br> _Polygon Mesh Processing_ [Botsch et al. 2008] <br> _**[HW 00 assigned](https://github.com/alecjacobson/geometry-processing-introduction), due 17/09/2018**_ <br> _**[Fill in final project choices](https://goo.gl/forms/iCkeHqYRszYyufV42), due 17/09/2018**_
| Tuesday, 18/09/2018 | tangents and normals, geometry vs. topology, orientability, discrete topology, meshes, data structures <br>  _**[HW 01 assigned](https://github.com/alecjacobson/geometry-processing-mesh-reconstruction) due 28/09/2018**_
| Tuesday, 25/09/2018 | [**Acquisition & reconstruction**](lecture-notes/mesh-reconstruction.md), characteristic function, spatial gradient<br> "Poisson surface reconstruction" [Kazhdan et al. 2006] <br> quadratic energy minimization, marching cubes <br> _**[HW 02 assigned](https://github.com/alecjacobson/geometry-processing-registration) due 08/10/2018**_ |
| Tuesday, 02/10/2018 | [**Alignment & registration**](lecture-notes/registration.md) Hausdorff distance, integrated closest point distance<br> "Object modelling by registration of multiple range images" [Chen & Medioni 1991] <br> "A method for registration of 3-D shapes" [Besl & McKay 1992] <br> "Efficient Variants of the ICP Algorithm" [Rusinkiewicz & Levoy 2001] <br> "Sparse Iterative Closest Point" [Bouaziz et al. 2013] <br> point-to-plane distance, iterative closest point, orthogonal Procrustes problem
| Tuesday, 09/10/2018 | [**Surface fairing & denoising**](lecture-notes/smoothing.md), 1D smoothing flow, 1D energy-based smoothing, PDE, Implicit Time integration<br> [Discrete Differential Geometry "Forum"](http://ddg.cs.columbia.edu)<br> "Curve and surface smoothing without shrinkage" [Taubin 1995] <br> "Skeleton extraction by mesh contraction" [Au et al. 2008]<br> "Can Mean-Curvature Flow Be Made Non-Singular" [Kazhdan et al. 2005]  <br> Spatial Laplacian, calculus of variations, Green's Identity, role of trace in quadratic energies, minimizing quadratic energies in libigl <br> _**[HW 03 assigned](https://github.com/alecjacobson/geometry-processing-smoothing) due 15/10/2018**_   
| Tuesday, 16/10/2018 | [**Shape deformation**](lecture-notes/deformation.md), continuous deformation, pointwise mappings, energy-based model, handle-based deformation, local distortion mesure, gradient-based distortion, Laplacian-based distortion, as-rigid-as-possible <br> "An intuitive framework for real-time freeform modeling" [Botsch & Kobbelt 2004] <br> "On linear variational surface deformation methods" [Botsch & Sorkine 2008] <br> "As-rigid-as-possible surface modeling" [Sorkine & Alexa 2007] <br> "Bounded Biharmonic Weights for Real-Time Deformation" [Jacobson et al. 2010] <br> _**[HW 04 assigned](https://github.com/alecjacobson/geometry-processing-deformation) due 25/10/2018**_
| Tuesday, 23/10/2018 | [**Surface parameterization**](lecture-notes/parameterization-ryan-schmidt.pdf), texture mapping, mass-spring methods, graph drawing, harmonic maps, least squares conformal mapping, local parameterization, discrete exponential map, stroke parameterization <br> "Intrinsic parameterizations of surface meshes" [Desbrun et al. 2002] <br> "Least squares conformal maps for automatic texture atlas generation" [Lévy et al. 2002] <br> "Spectral conformal parameterization" [Mullen et al. 2008] <br> "Interactive Decal Compositing with Discrete Exponential Maps" [Schmidt et al. 2006] <br>  _**[HW 05 assigned](https://github.com/alecjacobson/geometry-processing-parameterization), due 30/10/2018**_     
| Tuesday, 30/10/2018 | [**Curvature & surface analysis**](lecture-notes/curvature.md) Planar curves, tangents, arc-length parameterization, osculating circle, curvature, turning number theorem, discrete curvature, normal curvature, minimum/maximum/mean curvature Principal curvature, Gauss map, Euler's theorem, shape operator, Gaussian curvature <br> "Computing Discrete Minimal Surfaces and Their Conjugates" [Pinkall and Polthier 1993] <br> "Gaussian Curvature and Shell Structures" [Calladine 1986] <br> "Discrete differential-geometry operators for triangulated 2-manifolds" [Meyer et al. 2002] <br> _Elementary Differential Geometry_, [Barret O'Neill 1966  <br> _Discrete Differential Geometry: An Applied Introduction_, SIGGRAPH Course, [Grinspun et al. 2005] <br> _**[HW 06 assigned](https://github.com/alecjacobson/geometry-processing-curvature) due 13/11/2018**_
| Tuesday, 06/11/2018 | **_No Lecture: FAS Reading week._** 
| Tuesday, 13/11/2018 | **Subdivision surfaces** <br> "Subdivision for Modeling and Animation" [Zorin et al. 2000]
| Tuesday, 20/11/2018 | **Mesh decimation, simplification, remeshing**  <br> "Surface Simplification Using Quadric Error Metrics" [Garland and Heckbert 1997] <br> "A Remeshing Approach to Multiresolution Modeling" [Botsch and Kobbelt 2004]
| Tuesday, 27/11/2018 | [**Signed distances**](lecture-notes/signed-distance.md), Offset surfaces, inside-outside segmentation, medial axis, isosurface/level sets, signed distances to polyhedra, parity counting, winding number <br> "Signed Distance Computation using the Angle Weighted Pseudo-normal" [Baerentzen & Aanaes 2005] <br> "3D distance fields: a survey of techniques and applications" [Jones et al. 2006] <br> "Robust Inside-Outside Segmentation using Generalized Winding Numbers" [Jacobson et al. 2013]
| Tuesday, 04/12/2018 | **Final project presentations** |

> Cutting room floor: **Quad meshing**, **Subdivision surfaces**, **Constructive
> solid geometry**, **Voxelization**

## Slack

dgp-graphics.slack.com, \#geometry-processing channel, ask dgp member for invite

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


<!-- 
cat header.md README.md | multimarkdown --process-html -o README.html && open README.html
-->
