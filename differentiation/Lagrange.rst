.. _Lagrange-multiplier:

###################
Lagrange Multiplier
###################

This section is about the method of Lagrange multipliers.  Suppose we have a function :math:`f(x,y)` or :math:`f(x,y,z)` and we want to maximize it, but the variables are not independent, e.g. :math:`g(x,y) = c` where :math:`c` is a constant.  

+++++++
Example
+++++++

The method of Lagrange multipliers is to find a solution to this equation

.. math::

    \nabla f = \lambda \nabla g

If there is a constrained max (or min), it will satisfy this equation.

Suppose

.. math::

    f(x,y) = xy

    g(x,y) = x + y = 10

This could be the famous maximum area problem where :math:`x` and :math:`y` are the sides of a rectangle, the semi-perimeter is given, and the objective is to pick :math:`x` and :math:`y` to maximize the area.  We see a solution for this in Calculus 1, namely, solve :math:`g` for one of the variables.

.. math::

    x = 10 - y

and substitute:

.. math::

    h(y) = (10-y)y = 10y - y^2

    h'(y) = 10 - 2y = 0

    h''(y) = - 2

Since the second derivative is :math:`< 0`, this is a maximum, and the solution is :math:`y = 5, x = 5`.

Using the Lagrange method we say

.. math::

    f(x,y) = xy
    
    f_x = y, \ \ \ f_y = x

    g(x,y) = x + y = 10

    g_x = g_y = 1

We say:

.. math::

    \nabla f = \lambda \nabla g

meaning:

.. math::

    f_x = \lambda g_x

    f_y = \lambda g_y

Plugging in, we obtain two equations

.. math::

    f_x = y = \lambda g_x = \lambda

    f_y = x = \lambda g_y = \lambda
    
So, clearly :math:`x=y`

+++++++
Example
+++++++

Corral gives this problem.  Find the points on the circle :math:`x^2 + y^2 = 80` that are either closest to or furthest from the point :math:`P = (1,2)`.

Here is the diagram from Corral

.. image:: /figs/Corral1.png
   :scale: 50 % 

The circle equation is our *constraint*.  We need to find an equation for distance, which we will then maximize.

.. math::

    d = \sqrt{(1-x)^2 + (2-y)^2}

We can simplify by saying that if :math:`d^2` is a min or max, then so is :math:`d`.  So now we have

.. math::

    f(x,y) = d^2 = (1-x)^2 + (2-y)^2 = 1 - 2x + x^2 + 4 - 4y + y^2

    f_x = -2 + 2x

    f_y = -4 + 2y

    g_x = 2x

    g_y = 2y

The Lagrange equations:

.. math::

    \nabla f = \lambda \nabla g

    f_x = \lambda g_x

    f_y = \lambda g_y

Plugging in, we obtain two equations

.. math::

    -2 + 2x = \lambda 2x

    -4 + 2y = \lambda 2y

Solve for :math:`\lambda` and set them equal

.. math::

    \frac{-4 + 2y}{2y} = \frac{-2 + 2x}{2x}

    \frac{-2 + y}{y} = \frac{-1 + x}{x}

    -2x + xy = -y + xy

    y = 2x

Since :math:`x^2 + y^2 = 80`

.. math::

    x^2 + 4x^2 = 80

and so :math:`x= \pm 4` and the solutions are :math:`(4,8)`, :math:`(-4,-8)`. 

Here is the diagram again

.. image:: /figs/Corral1.png
   :scale: 50 % 

+++++++
Example
+++++++

Auroux gives this problem:  on the curve of the hyperbola :math:`xy=3`, find the point closest to the origin.

The distance to the origin is 

.. math::

    d = \sqrt{x^2 + y^2}

but we can simplify things a bit because if :math:`d^2` is a minimum, then :math:`d` is a minimum.  So the function we need to minimize is

.. math::

    f(x,y) = d^2 = x^2 + y^2

subject to the constraint :math:`xy = 3`.

The graph of :math:`f(x,y)` is a *surface*---a paraboloid with circular cross-section---with apex at :math:`(0,0,0)`, and opening up.  :math:`x^2 + y^2` is a *level curve* of :math:`f`, at the value :math:`f=a`.

In this figure we have the situation as described, except that for this figure :math:`xy = 1/2`.

.. image:: /figs/lagrange.png
   :scale: 50 % 

The idea of the method is that, at the maximum, the circle just touches the hyperbola.  And at the point of contact, the gradient of the circle function is parallel to the gradient of the hyperbola function, so the two are equal when one is multiplied by a constant that is usually designated :math:`\lambda`.

.. math::

    \nabla f = \lambda \nabla g

+++++++++++++++++
Two more problems
+++++++++++++++++

Before we actually solve this problem, I want to go ahead and look at two more (from Paul's *Calculus Notes*), that are a little easier.  The first is to find the dimensions of a rectangular box with maximum volume, subject to the constraint that the surface area is fixed.

.. math::

    V = xyz

    A = 2(xy + xz + yz) = \text{constant}

The Lagrange equations:

.. math::

    \nabla V = \lambda \nabla A

    V_x = yz, \ \ \ V_y = xz, \ \ \ V_z = xy
    
    A_x = 2(y + z), \ \ \ A_y = 2(x + z), \ \ \ A_z = 2(x + y)

So from :math:`\nabla V = \lambda \nabla A` we have then three equations (plus a fourth:  the one for area above).

.. math::

    yz = 2 \lambda (y+z)
    
    xz = 2 \lambda (x+z)

    xy = 2 \lambda (x+y)

Paul uses a nice trick to solve this.  Take the first two equations, multiply eqn. 1 by :math:`x` and eqn. 2 by :math:`y`:

.. math::

    xyz = 2 \lambda x(y+z)

    xyz = 2 \lambda y(x+z)

    xy + xz = xy + yz

    x = y

By symmetry, :math:`x=y=z`.

Our second problem is a little easier.  Maximize :math:`f(x,y) = 5x-3y` subject to the constraint that :math:`x^2 + y^2 = 136`.

.. math::

    f_x = 5 = \lambda g_x = \lambda 2x

    f_y = -3 = \lambda g_y = \lambda 2y

    \lambda = \frac{5}{2x} = -\frac{3}{2y}
    
    y = - \frac{6x}{10}
    
Resist the urge to factor out the :math:`2`.

To solve this, use the constraint:

.. math::

    x^2 + y^2 = 136

    x^2 + \frac{36}{100}x^2 = 136

    x^2 \frac{136}{100} = 136
    
    x^2 = 100

    x = \pm 10
    
    y = y \pm 6

    \lambda = \pm \frac{1}{4}

Looking at the original equation, it is obvious that this is a maximum when :math:`x>0` and :math:`y<0`.

+++++++++++++++++++++++++++
Finally solving our problem
+++++++++++++++++++++++++++

In the original problem, we have

.. math::

    f(x,y) = x^2 + y^2

    f_x = 2x

    f_y = 2y

    g(x,y) = xy = c

    \nabla f = \lambda \nabla g

so the two equations we get are

.. math::

    2x - \lambda y = 0

    \lambda x - 2y = 0

As we did above, we can solve for :math:\lambda` in both equations and set them equal:

.. math::

    \lambda = \frac{2x}{y} = \frac{2y}{x}
    
    x^2 = y^2
    
    x = \pm y

Auroux uses some linear algebra trickery to solve this.  A matrix equation :math:`A\mathbf{v}=\mathbf{0}` has solutions other than :math:`\mathbf{v}=0` only if det :math:`(A) = 0`.  So that's what we do:

.. math::

    A =
    \begin{bmatrix} 
      2  &  -\lambda   \\ 
      \lambda  &  -2  
    \end{bmatrix}

The determinant is

.. math::

    -4 + \lambda^2 = 0 

    \lambda = \pm 2

Using :math:`2x - \lambda y = 0`,for :math:`\lambda = 2`, we obtain :math:`2x-2y=0` and :math:`x=y`, while for :math:`\lambda = -2`, we obtain :math:`2x+2y=0` and :math:`x=-y`.

Exactly as you would predict from the figure.  
