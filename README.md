# Adaptive Mesh Refinement 
The main problem investigated in this project is the 2d plane stress elasticity
problem for a L-shaped domain.
# Goals:
In this elasticity problem, there is also a body force acting on the entire structure
in the downward direction. From elasticity studies we know that the region
connecting the overhanging portion to the top  xed boundary will be highly
stressed and as a result the error in these elements will be high as well. I expect
that the adaptive mesh re nement process will capture these regions of high
internal stresses, consequently more error prone, and the mesh will be re ned
in this region to lower the peak in the internal stress values and subsequenly a
reduction in the error norm.

#Implementation
The adaptive re nement algorithm follows a cycle of
solve->estimate->mark->refine.
We start with solve. A structural  nite element solver was fully developed
in-house coupled with the ['https://pypi.org/project/MeshPy/'] grid generator. Linear triangular elements
was used for meshing the design domain having 2 degrees of freedom at each
vertex. A body force to simulate loading due to gravity was impelmented. The
undeformed mesh (blue) and the deformed mesh (green) is shown in Figure.
After calculating the required values on the initial mesh, we estimate the errors
in the elements. For this we use a posteriori error estimator.
![](https://github.com/anurag-bha/AdaptiveFiniteElements/blob/main/Figs/Undeformed%20and%20deformed%20FEA%20meshes.png)

We will demonstrate how GitHub Actions can be used to display a spectrogram of a snippet from an underwater audio stream.

* [`.github/workflows/Python_env.yml`](https://github.com/anurag-bha/AdaptiveFiniteElements/blob/main/.github/workflows/Python_env.yml)
* workflow steps:
  * upload figures to GitHub 

After the workflow is executed the adaptively refined mesh file is updated in the repo and is visualized below along with the deformed file
Refined Mesh            |  Original & Deformed Mesh
:-------------------------:|:-------------------------:
![](https://github.com/anurag-bha/AdaptiveFiniteElements/blob/main/Figs/Adaptive%20mesh%20refinement.png)  |  

