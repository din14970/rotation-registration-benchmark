## Benchmarking in-plane rotation finding methods
What is the fastest way to find the rotation angle between two images that are rotated relative to eachother?
In this notebook we test 3 ways: an FFT based approach, a direct approach using numpy (also working for cupy), and a "loopy" numba JIT implementation.
The conclusion is that the FFT based approach is fast but the "loopy" version outperforms if one of the images is very sparse and can be described in a sparse way.
See the notebook [here](https://nbviewer.jupyter.org/github/din14970/rotation-registration-benchmark/blob/master/FFT_vs_shift.ipynb).
