# CudaFilter
CudaFilter is a sample application showcasing the use of the Alea GPU library for general-purpose GPU (GPGPU) computations, specifically for calculating terrain slopes. The project demonstrates the viability and performance benefits of using CUDA for intensive computational tasks in geographical data processing.

Sample app using Alea GPU library for calculating terrain slope with CUDA.

The main idea behind the application is to show viability of using Alea GPU library for GPGPU computations. Thus, it is not a complete solution - the result itself is not georeferenced etc. Theoreotically, calculating the slope in angles does not add anything to the final gradient product - percentage would work just as well. I did it only to show the performance benefits when calculating the angles themselves.

A few things that can be improved:

the data portions for GPU slope are calculated basing on only on image width. Ideally it, should take into account the larger of two components. The data portions should be created in such a way to ensure that inner Gpu.Parallel.For has more iterations than outer for.
perhaps it would be even better to get rid of matrix and store everything in simple arrays
the input file should really not be read in a single shot. We might be missing not only on VRAM, but also simply RAM.
Input heightmap (DEM):
![image](https://github.com/user-attachments/assets/2f29dd02-a004-43a8-acc4-da3bf9562af4)
Output slope gradient:
![image](https://github.com/user-attachments/assets/08395ae2-e92e-487a-a7af-3fc066625bbf)
