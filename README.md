# axis_angle_rotation
Some notes on axis angle rotation

To build some intuition (hopefully and not confuse more than help ..) the approach is to first show how you can rotate a vector v in 2D vector arithmetic and then rearrange it into a matrix.
(The math behind it is that vector arithmetic is a linear transformation and matrices are linear transformations as well, so we start with vectors. See [Khan Academy - Linear algebra course](https://www.khanacademy.org/math/linear-algebra/matrix-transformations/linear-transformations/v/linear-transformations) ).

And then how to rotate a 3D vector with vector arithmetic and then rearrange over to a 3D rotation matrix (which rotates a vector v around an given axis).

The tex file is written with pytex so it's a bit annoying to compile. That is why I added the pdf and rendered a png in the readme:

The 3D rotation formula is similar to that used in [Ravi Ramamoorthi's course](https://www.youtube.com/watch?v=LazSPnaoJ_Q&t=482s) (matrix part). Also [Mathomas videos](https://youtu.be/q-ESzg03mQc) are a nice resource on this topic.

## possible implementation
An (inefficient) implementation in python and numpy could look like:

    import numpy as np
    # input: normalized rotation axis vector n, angle theta (radians)
    # output: 3x3 rotation matrix
    def axis_angle_rotation(n, theta):
        def skew(n): # get skew symmetric matrix by transformation of base vectors
            nxe1 = np.cross(n, (1, 0, 0))   # n x e1
            nxe2 = np.cross(n, (0, 1, 0))   # n x e2
            nxe3 = np.cross(n, (0, 0, 1))   # n x e3
            return np.column_stack([nxe1, nxe2, nxe3])  # define matrix by transformed column vectors

        P = np.outer(n, n)  # outer product of n with n (nn^T) is a matrix
        I = np.identity(3)
        K = skew(n)
        return P + np.cos(theta) * (I - P) + np.sin(theta) * K

## Derivation
![axis_angle](https://user-images.githubusercontent.com/22398803/149604737-1b46491a-c348-4c28-9cf1-7ee9ed9c2ba2.png)

