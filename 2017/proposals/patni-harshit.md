# Developing and expanding CuPy library

Tanish Sharrma, NumFocus 2019

E-Mail : tanishsharrma22@gmail.com
Mobile : +91-7838063629 (Whatsapp as well)
github : @TanishSharrma
LinkedIn : linkedin.com/in/TanishSharrma
Resume : http://tanish.ueuo.com/cv.pdf


## Abstract

CuPy is an open-source matrix library accelerated with NVIDIA CUDA. It also uses CUDA-related libraries including cuBLAS, cuDNN, cuRand, cuSolver, cuSPARSE, cuFFT and NCCL to make full use of the GPU architecture. Aiming to bring Numpy syntax coding into the modern age of GPU calculations by adding advanced FFT functions into CuPy.

| **Intensity** | **Involves**  | **Mentors** |
| ------------- | --------------|------------ |
| Intermediate  | Python, NumPy |   asi1024   |
|               | SciPy & CUDA  |             |
                  
## Brief Roadmap and Aim

Expand the number of functions available for use on the GPU to allow more code to execute transparently on the GPU. Also, CuPy covers many of the functions that are provided by Numpy, but not all of them. To review the Numpy functions that CuPy doesn't cover yet, and implement them in CuPy to use the full speed of the GPU.

Adding SciPy functions along with adding new Statistical functionalities to the project.

To Formalize CuPy Benchmark for code testing, when doing Continuous Integration testing for CuPy, there isn't a good estimator for the speed of the code. CuPy is all about improved speed of calculation on the GPU, so speed matters. Develop a comprehensive benchmark for CuPy to help assess how much speed enhancements help, and make sure that other code changes don't damage performance.

## Pre-GSoc Project Commits, Pull Requests and Issues and community work done :

### 1) Pull Request and commit : Added a new feature and resolved for Issue #2107 : bincount - Complex Weights :

Issue #2107 (brought up by another use) :
"bincount is a useful way to average values in an array with variable length bins (another is np.add.at, but that is not implemented here). This is also described in the numpy.bincount manual (https://docs.scipy.org/doc/numpy/reference/generated/numpy.bincount.html).
However, if I give a complex64 array as the weights parameter, cupy.bincount fails with a NVRTCError/CompileException:"

Resolved :

Added a feature in "cupy.bincount" which will now be able to calculate even if the weights parameter is an array of complex         numbers (taken into account that not all values may be complex, hence setting a x+0j value to integer/float values). The calculation would be to do bincount twice (with real/imaginary part of the weight) [as suggested by "@kmaehashi"]

### 2) Submitted an Issue : CuPy not accepting list data types for operations #2138

For any function on a list(array) data type, Cupy gives an error unless the array has been defined as a cupy.array(). In, numpy however, the list data type is accepted regardless of it being passed as numpy.array() or not.

a = [10,15]
b = cupy.log(a)

This won't work in Cupy but will work in Numpy. a = cupy.array([10,15]) would work.
TypeError: Unsupported type <class 'list'>
This could cause problems for people shifting from Numpy to Cupy.

### 3) Resolve Suggested

Suggested a resolve for an installation Issue by downloading the Microsoft Visual C++ Build Tools for installation of CuPy in Windows.

### May 1th - May 28th, **Community Bonding Period**

- Before the official time period begins I will do some tasks listed under
[MEP21](http://matplotlib.org/devel/MEP/MEP21.html): color and cm refactor.
This will greatly help in understanding the current implementation of
normalization and color mapping tools in Matplotlib. Some tasks that can be
done as part of this are:
    - Tidying up namespace
    - Defining a "Color" tuple
    - Improving construction of colormap by changing current dictionary approach
    - Analyzing  the feasibility of renaming `cm` module to something more
      descriptive. It will be a major API change so this will be done only if
      its pros outweighs cons
- Set up a blog
- Along with this I will continue to solve issues on github

### May 29th - June 3rd

- Decide on how API will be exposed to users as new API or as extension of
ScalerMappable
- Start working on normalizers

### June 5th - June 9th

- Finish up normalizers
- Write tests
- Starting working on color map that maps unit circle or square to rgba
- Write blog

### June 12th - June 16th

- Finish up color maps
- Debug and test
- Write tests

### June 19th - June 23th, **End of Phase 1**

- Complete any unfinished work in Phase 1
- Write documentation for code written so far
- Write blog for Phase 1

### June 26 - June 30th, **Begin of Phase 2**

- Make API for exposing normalizers and color maps to user
- Test new API
- Document the API so that it is exposed to users

### July 3rd - July 7th

- Start implementing 2D color bar
- Write blog

### July 10th - July 14th

- Continue implementing 2D color bar

### July 17th - July 21th, **End of Phase 2**

- Complete any unfinished work of Phase 2
- Write blog for Phase 2

### July 24th - July 28th, **Begin of Phase 3**

- Research on perceptually friendly colormaps

### July 31st - August 4th

- Develop 2D colormaps

### August 7th - August 11th

- Test and document colormaps
- Write blog

### August 14th - August 18th

- Write examples for Matplotlib gallery to demonstrate 2D color maps

### August 21st - August 25th, **Final Week**

- Buffer period for any unfinished work
- Write blog for Phase 3
- Clean up code

### August 28th - August 29th, **Submit final work**

## Future works

- In future the project can be extended to higher dimensions by mapping to
quaternions as well.
- Different types of colormaps can be added

## Open Source Development Experience

- (Merged) [#8094](https://github.com/matplotlib/matplotlib/pull/8094) Cleaned up documentation by removing an example
- (Merged) [#8097](https://github.com/matplotlib/matplotlib/pull/8097) Improved the code to use plt.gca instead of plt.axes
- (Merged) [#8154](https://github.com/matplotlib/matplotlib/pull/8154) Merged fill_demo and fill_demo_features examples
- (Merged) [#8190](https://github.com/matplotlib/matplotlib/pull/8190) Added link to Gitter channel in readme
- (Merged) [#8234](https://github.com/matplotlib/matplotlib/pull/8234) Fixed broken Gitter badge
- (Merged) [#8343](https://github.com/matplotlib/matplotlib/pull/8343) Made ArrowStyle docstrings numpydoc compatible
- (Open) [#8336](https://github.com/matplotlib/matplotlib/pull/8336) Merged three streamplot examples into one plot with subplots
- (Open) [#8157](https://github.com/matplotlib/matplotlib/pull/8157) Added 'which' kwarg to autofmtxdate and wrote tests

## Other Experiences

- [AI-Bot](https://github.com/patniharshit/Ultimate-Tic-Tac-Toe) in python
  for 4X4 Ultimate-Tic-Tac-Toe
- [Brick-Breaker](https://github.com/patniharshit/Brick-Breaker), a 2d shooter
  game in OpenGL
- [Bloxorz](https://github.com/patniharshit/Bloxorz), a 3d puzzle game in OpenGL

## Why this project?

Currently there are no multidimensional colormaps in Matplotlib. This is a
big nuisance if we want to modulate the color and opacity based on data in
different dimensions independently. This project has been requested for a long
time by people in neuroscience, astronomy etc.
Here are some of those requests :

- [#4369](https://github.com/matplotlib/matplotlib/issues/4369)
- [Bivariate Colormaps](http://stackoverflow.com/questions/15207255/is-there-any-way-to-use-bivariate-colormaps-in-matplotlib)

Having used Matplotlib for displaying graphical information several times, I
wanted to give something back to the community. I am the right person to do
this project because not only I want to contribute to Open Source but I have
also worked closely with the community for last month so I have good
understanding of workflow.

## Appendix

### About Me

I am a sophomore at International Institute of Information Technology,
Hyderabad majoring in Computer Science. I have intermediate proficiency in
Python and have worked on several projects with it. I am also an active
contributor of Matplotlib for some time.

### Contact
|          |                                                        |
|----------|--------------------------------------------------------|
| Name     | Harshit Patni                                          |
| Email    | patniharshit@gmail.com                                 |
|          | harshit.patni@students.iiit.ac.in                      |
| Github   | [patniharshit](https://github.com/patniharshit)        |
| Gitter   | patniharshit                                           |

### Availability

I don't have any commitments in summer and GSOC will be my full time job.
My summer vacations starts on 27 April and college reopens in last week of
July.

* **Time Zone :** Indian Standard Time (IST) UTC +5:30
*  **Hours per week :** 35-40 hours(during vacations), this may go down to
30-35 hours in August
