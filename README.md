## Benchmarking in-plane rotation finding methods
What is the fastest way to find the rotation angle between two images that are rotated relative to eachother?
In this notebook we test 5 ways: 

1. an FFT based cross-correlation approach
2. the FFT based approach on the GPU
3. a direct approach using numpy
4. the same direct approach using cupy
5. a "loopy" numba JIT implementation.

The conclusion is that the FFT based approach is fast but the "loopy" version outperforms if one of the images is very sparse and can be described in a sparse way.
The GPU implementations are substantially faster but "bottom out" faster for high sparsity than CPU implementations.
See the notebook [here](https://nbviewer.jupyter.org/github/din14970/rotation-registration-benchmark/blob/e29061c10d2d4e8366f9e99d986dca79e986765d/FFT_vs_shift.ipynb).
