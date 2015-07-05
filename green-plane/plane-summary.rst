.. _plane-summary:

#########
Summary 1
#########

This short write-up will summarize the first two of the four fundamental theorems of vector calculus.  I hope this will help me to remember them.

First, though, a word about curl.  Curl measures the rotation of a vector field (its absolute value is twice the angular momentum).  As an example, if a two dimensional field :math:`\mathbf{F}` has components :math:`<M,N>`, then

.. math::

    \text{curl} \ \mathbf{F} = N_x - M_y 

As we'll see, the calculation of :math:`\text{curl} \ \mathbf{F}` produces a vector, in this case it points out of the plane.  When we calculate with it in 2D we are implicitly dotting it with :math:`\hat{\mathbf{k}}`.

Our convention is that we go on a curve around a region with :math:`R` on our left, then the curl points up.

If the value of :math:`\text{curl} \ \mathbf{F}` is zero, then the work done going around the closed curve is also zero, alternatively if the curl is non-zero, work is done.  Think of swimming in a whirlpool.  Against the flow it is hard going, whereas with the flow, it's easy.

In our theorems, the curl will always be associated with the line integral for work.

The work done in moving along a curve :math:`C` is

.. math::

    W = \int_C \mathbf{F} \cdot d\mathbf{r}  

    = \int_C \mathbf{F} \cdot \hat{\mathbf{T}} \ ds 

In three dimensions, we use the "del" operator

.. math::

    \nabla = \ < \frac{\partial}{\partial x},\frac{\partial}{\partial y},\frac{\partial}{\partial z} > 

The curl of :math:`\mathbf{F}` is

.. math::

    \nabla \times \mathbf{F} 

For :math:`\mathbf{F} = \ <P,Q,R>`

.. math::

    \nabla \times \mathbf{F} =  \ <R_y-Q_z,P_z-R_x,Q_x-P_y> 

which is basically impossible to remember except by using this convenient device

.. math::

    \begin{vmatrix}
    \hat{i}  &  \hat{j} & \hat{k} \\
    \frac{\partial}{\partial x}  &  \frac{\partial}{\partial y} & \frac{\partial}{\partial z} \\
    P  &  Q & R \\
    \end{vmatrix}

In two dimensions :math:`R=0` and also :math:`P_z` and :math:`Q_z` are both zero, so this equation reduces to the one we saw above (substituting :math:`M` for :math:`P` and :math:`N` for :math:`Q`).

A basic fact in vector calculus is that if the field is the gradient of a potential function, the curl is zero.  Let the function be :math:`f` and the field :math:`\mathbf{F} = \nabla f`, then :math:`M=f_x` and :math:`N=f_y`.  Then the curl is :math:`f_{yx}- f_{xy}`, but for any such function

.. math::

    f_{xy} = f_{yx} 

===========
Calculating
===========

Let's look again at

.. math::

    W = \int_C \mathbf{F} \cdot d\mathbf{r} 

    = \int_C \mathbf{F} \cdot \hat{\mathbf{T}} \ ds 

This can be written as

.. math::

    = \int_C M \ dx + N \ dy  

One way to see this is to say

.. math::

    d\mathbf{r} = \frac{d}{dt} \mathbf{r} \ dt = \ <\frac{dx}{dt},\frac{dy}{dt}> \ dt 

so when we do the dot product with :math:`\mathbf{F}`, we get what we wrote above.

There is another important integral to be explained below

.. math::

    \int_C \mathbf{F} \cdot \hat{\mathbf{n}} \  ds = \int_C -N \ dx + M \ dy  

It's really important to appreciate that although these equations look something like a double integral, they are *not*.  We will have a parametrization of the curve in terms of :math:`t` (or :math:`x` or :math:`\theta`), and a single integral like :math:`\int_C \ [ \ \ ] \ dt`.

============
Green---work
============

We start with two theorems in the plane (typically the :math:`xy`-plane).  These are called Green's Theorem for work, and Green's Theorem for flux.

Green's Theorem for work states that for a closed path

.. math::

    \oint \mathbf{F} \cdot d\mathbf{r}  = \iint_R \ \nabla \times \mathbf{F} \ dA 

One sticky point I had here is that the curl produces a vector, yet the formula is usually given as above.  That's because this is a special case of Stokes theorem where the term on the right is really

.. math::

    (\nabla \times \mathbf{F}) \cdot \hat{\mathbf{k}} \ dA 

which (since :math:`\nabla \times \mathbf{F} ` is parallel to :math:`\hat{\mathbf{k}}`) gives what we have above.

Alternatively

.. math::

    \int_C M \ dx + N \ dy = \iint_R (N_x - M_y) \ dx \ dy 

The work done along a closed path around :math:`R` is equal to the double integral over :math:`R` of the curl of :math:`\mathbf{F}`.  Remember the whirlpool.

============
Green---flux
============

Flux is flow across a curve, or in :math:`R3`, through a surface.

Green's Theorem for flux (in the plane) states that for a closed path :math:`C` over a region :math:`R`

.. math::

    \int_C \mathbf{F} \cdot \hat{\mathbf{n}} \  ds = \iint_R \ \nabla \cdot \mathbf{F} \ dA 

Alternatively

.. math::

    \int_C M dy - N dx =  \iint_R \ (M_x + N_y) \ dx \ dy 

Another use of the "del" operator is the divergence of :math:`\mathbf{F}`

.. math::

    \nabla \cdot \mathbf{F} 

if :math:`\mathbf{F} = \ <M,N>`

.. math::

    \nabla \cdot \mathbf{F} = M_x + N_y 

The divergence of a vector field is a scalar quantity.  It measures the net production (or disappearance) of the "substance" that flows in a vector field.  If there are no sources or sinks in a region, the divergence of :math:`\mathbf{F}` will be zero.

Restating the theorem:

.. math::

    \oint \mathbf{F} \cdot \hat{\mathbf{n}} \ dS  = \iint_R \ \nabla \cdot \mathbf{F} \ dA 

Breaking this down, on the left hand side of the first version, :math:`\hat{\mathbf{n}}` is the unit vector \emph{orthogonal} to :math:`\hat{\mathbf{T}}`.  Since :math:`\hat{\mathbf{n}}` and :math:`\mathbf{n}` are orthogonal to :math:`\hat{\mathbf{T}}` and :math:`d\mathbf{r}`, the dot product with :math:`<dx,dy>` must equal zero.  Hence, we should have

.. math::

    \hat{\mathbf{n}} \ ds = \ <\frac{dy}{dt},-\frac{dx}{dt}> dt 

Another way to think about this is that we rotate by

.. math::

    \begin{bmatrix}
    \ 0  &  1 \\
    -1  &   0  \\
    \end{bmatrix}
    \begin{bmatrix}
    dx  \\
    dy  \\
    \end{bmatrix}
    =
    \begin{vmatrix}
    \ \ dy  \\
    -dx  \\
    \end{vmatrix}

so when we compute :math:`\mathbf{F} \cdot \ <dy,-dx>` we get :math:`\int_C M \ dy - N \ dx`.  Putting it all together, we have

.. math::

    \int_C \mathbf{F} \cdot \hat{\mathbf{n}} \  ds =  \iint_R \ \nabla \cdot \mathbf{F} \ dA  

    \int_C M dy - N dx =  \iint_R \ (M_x + N_y) \ dx \ dy 

Here, the expression on the right *is* a double integral.
