# axis_angle_rotation
Some notes on axis angle rotation

To build some intuition (hopefully and not confuse more than help ..) the approach is to first show how you can rotate a vector v in 2D vector arithmetic and then rearrange it into a matrix.
(The math behind it is that vector arithmetic is a linear transformation and matrices are linear transformations as well, so we start with vectors. See [Khan Academy - Linear algebra course](https://www.khanacademy.org/math/linear-algebra/matrix-transformations/linear-transformations/v/linear-transformations) ).

And then how to rotate a 3D vector with vector arithmetic and then rearrange over to a 3D rotation matrix (which rotates a vector v around an given axis).

The tex file is written with pytex so it's a bit annoying to compile. That is why I added the pdf and rendered a png in the readme:

The 3D rotation formula is similar to that used in [Ravi Ramamoorthi's course](https://www.youtube.com/watch?v=LazSPnaoJ_Q&t=482s) (matrix part). Also [Mathomas videos](https://youtu.be/q-ESzg03mQc) are a nice resource on this topic.


![axis_angle](https://user-images.githubusercontent.com/22398803/148301326-be78a794-4dda-4fac-b716-a70d683ccbad.png)
