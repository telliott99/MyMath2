.. _line-integrals:

####################
Basic Line Integrals
####################

A straightforward application of a line integral is to find the length of a curve.  A more sophisticated one yields the work done when moving along a curve, and there are certainly others.

The basic formula can be derived by doing algebra with differentials.  Think of a small element of the path of the curve, :math:`\Delta s`, as a right triangle with side lengths :math:`\Delta x` and :math:`\Delta y`.  

.. image:: /figs/arc-length.png
   :scale: 50 %

From Pythagoras we have:

.. math::

    (\Delta s)^2 = (\Delta x)^2 + (\Delta y)^2

In the limit, we will come to

.. math::
    
    ds^2 = dx^2 + dy^2 

"Divide and multiply" on the right by :math:`dx^2` to give

.. math::

    ds^2 = \frac{1}{dx^2} \ (dx^2 + dy^2) dx^2

    ds^2 = [1 + \frac{dy^2}{dx^2}] \ dx^2 

then take the square root

.. math::

    ds = \sqrt{1 + (\frac{dy}{dx})^2} \ dx 

    ds = \sqrt{1 + y' \ ^2} \ dx 

The arc length is just

.. math::

    s = \int ds = \int \sqrt{1 + y' \ ^2} \ dx 

In many cases :math:`x` and :math:`y` will be parametric equations (functions of a parameter like :math:`t`).  For that situation, we have the following approach:

.. math::

    \mathbf{c}(t) = \langle \ x(t), y(t) \ \rangle
      
    \mathbf{c}' = \langle \ \frac{dx}{dt}, \frac{dy}{dt} \ \rangle
    
    \lVert \mathbf{c}' \rVert = \sqrt{(\frac{dx}{dt})^2 + (\frac{dy}{dt})^2}
    
We can think of :math:`\lVert \mathbf{c}' \rVert` as the *speed*.  Speed times time is distance.

The formula for arc length as a function of time is then:

.. math::

    s = \int \lVert \mathbf{c}' \rVert \ dt
    
    = \int \sqrt{(\frac{dx}{dt})^2 + (\frac{dy}{dt})^2} \ dt

These two formulas can be connected in the following way.  We had that

.. math::
    
    (\Delta s)^2 = (\Delta x)^2 + (\Delta y)^2

and easily derived the first formula by "divide and multiply".

Now write:

.. math::

    \Delta s = \sqrt{(\Delta x)^2 + (\Delta y)^2}
    
    = \sqrt{(\frac{\Delta x}{\Delta t})^2 + (\frac{\Delta y}{\Delta t})^2} \ \Delta t

In the limit we will have that

.. math::

    ds = \sqrt{(\frac{dx}{dt})^2 + (\frac{dy}{dt})^2} \ dt
    
    = \sqrt{(x'(t))^2 + (y'(t))^2} \ dt

So

.. math::

    s = \int ds = \int \sqrt{(x'(t))^2 + (y'(t))^2} \ dt

=========
Example 0
=========

Suppose we look at the line from the origin to :math:`(1,2)` and we parametrize this line as a function of :math:`t`:

.. math::

    t = 0 \rightarrow 1
    
    x = t
    
    y = 2t
    
Using the first formula, we need :math:`y` in terms of :math:`x`:  :math:`y = 2x`:

.. math::

    s = \int \sqrt{1 + y' \ ^2} \ dx
    
    = \int \sqrt{1 + 2^2} \ dx 
    
    = \sqrt{5} x \ \bigg |_0^1 = \sqrt{5}
    
By the second formula

.. math::

    \frac{dx}{dt} = 1, \ \ \ \frac{dy}{dt} = 2

    s = \int \sqrt{(\frac{dx}{dt})^2 + (\frac{dy}{dt})^2} \ dt

    = \int \sqrt{1 + 2^2} \ dt
    
    = \sqrt{5} t \ \bigg |_0^1 = \sqrt{5}

Seems to work.

Manipulating differentials to go from one formula to the other, I just get into trouble.  But Pythagoras justifies the first formula, and velocity :math:`\times` time justifies the second.

=========
Example 1
=========

Here is another one where we already know the answer:  the arc length along the boundary of the circle of radius :math:`R` in the first quadrant.  Again, the formula is

.. math::

    ds = \sqrt{1 + (\frac{dy}{dx})^2} \ dx 

So we want

.. math::

    \int ds = \int_0^R  \sqrt{1 + (\frac{dy}{dx})^2} \ dx 

The circle is

.. math::

    x^2 + y^2 = R^2 

By implicit differentiation, we easily obtain

.. math::

    2x \ dx + 2y \ dy = 0

    \frac{dy}{dx} = -\frac{x}{y} 

    (\frac{dy}{dx})^2 = \frac{x^2}{y^2} 

So the integral is

.. math::

    = \int_0^R  \sqrt{1 + \frac{x^2}{y^2}} \ dx 

    = \int_0^R \frac{1}{y}  \sqrt{y^2 + x^2} \ dx 

    = R \int_0^R \frac{1}{y}  \ dx 

    = R \int_0^R \frac{1}{\sqrt{R^2-x^2}}  \ dx 

This can be solved in various ways.  Recall that

.. math::

    \int \frac{1}{\sqrt{1-x^2}} \ dx = \sin^{-1} x

We can use this as is, if we substitute:  :math:`u = x/R`

Here, we use the same trig substitution that gives the above result:

.. math::

    x = R \sin t 

    dx = R \cos t \ dt 

    \sqrt{R^2 - x^2} = R \cos t 

So we have

.. math::

    = R \int \frac{1}{R \cos t} R \cos t \ dt = R t 

The slightly tricky part is the limits on :math:`t`.  The lower limit was :math:`x=0`, so now we need :math:`R \sin t = 0`, which means that :math:`t=0`.  The upper limit was :math:`x=R`, so now we need :math:`R \sin t = R` so now :math:`t = \pi/2`.

The integral is :math:`\pi R/2` and the whole circumference is :math:`4` times that or :math:`C = 2 \pi R`.

Another, simpler way to do this calculation is to use the parametrized circle (:math:`x = \cos \theta, y = \sin \theta`).  Go back to the element of arc :math:`ds` given by Pythagoras:

.. math::

    ds^2 = dx^2 + dy^2 

    L = \int ds = \int \sqrt{dx^2 + dy^2}

    = \int \sqrt{\cos^2 \theta + \sin^2 \theta} \ d \theta 

    = \int \ d \theta 

Here, we can just go all the way around the circle from :math:`\theta = 0 \Rightarrow 2 \pi`.  And for a circle of radius :math:`a` we have :math:`a \cos \theta` and :math:`a \sin \theta` which gives a factor of :math:`a^2` under the square root, yielding an extra factor of :math:`a` in the end.

=========
Example 2
=========

Consider

.. math::

    y = x^2 

    \frac{dy}{dx} = 2x 

    ds = \sqrt{1 + (\frac{dy}{dx})^2} \ dx 

    ds =  \sqrt{1 + 4x^2} \ dx 

The arc length is the integral of :math:`ds`

.. math::

    L = \int  \sqrt{1 + 4x^2} \ dx 

    = 2 \int  \sqrt{(\frac{1}{2})^2 + x^2} \ dx 

This will be a minor challenge (see trig substitutions).  Rather than struggle with it, just set :math:`a = \frac{1}{2}` and look up the answer in a table of integrals

.. math::

    \int  \sqrt{a^2 + x^2} \ dx  = \frac{x}{2}\sqrt{a^2 + x^2} + \frac{a^2}{2} \ln \ | \ x + \sqrt{a^2 + x^2} \ | 

substitute back for :math:`a = 1/2`

.. math::

    \frac{x}{2}\sqrt{\frac{1}{4} + x^2} + \frac{1}{8} \ln \ | \ x + \sqrt{\frac{1}{4} + x^2} \ | 

Suppose the limits are :math:`x=1` and :math:`x=0`.  At the upper limit, we have

.. math::

    \frac{1}{2}(\sqrt{1.25}) + \frac{1}{8} \ \ln \ (1 + \sqrt{1.25}) 

    \sqrt{1.25} \approx 1.118  

    \ln (2.118) \approx 0.7505 

    (0.5)(1.118) + (0.125)(0.7505) = 0.559 + 0.0938 = 0.6528 

while at the lower limit the first term is :math:`0` and the second is

.. math::

    \frac{1}{8}\  \ln \frac{1}{2} = - (0.125)\  \ln 2 = - (0.125)(0.693) = -0.0866 

Subtracting

.. math::

    0.6528 + 0.0866 = 0.7394 

Remembering the factor of two we get :math:`1.4788`

Not exactly pretty, but it works.  Check by numerical integration

.. sourcecode:: python

    import scipy
    g = lambda x: sqrt(1 + 4*x**2)
    scipy.integrate.quad(g,0,1)

The result is given as :math:`1.47894`.

=========
Example 3
=========

Most commonly, especially when dealing with vector fields, we have :math:`x` and :math:`y` as functions of a parameter :math:`t`.

The vector field is :math:`\mathbf{F}` where

.. math::

    \mathbf{F} = \  \langle M,N \rangle 

or

.. math::

    \mathbf{F} = \  \langle P,Q,R \rangle 

and we are interested in the integral along the curve (for the work done by :math:`\mathbf{F}`):

.. math::

    \int_C \mathbf{F} \cdot d\mathbf{r} = \int_C \mathbf{F} \cdot \hat{\mathbf{T}} ds 

    = \int_C P \ dx + Q \ dy + R \ dz 

This last part probably seems like a magic trick.  We'll see how it's done in the next section.

Here I will just show how we evaluate it.  The crucial insight is provided by parametrization of the curve.  That gives us a function of a single variable.  Suppose

.. math::

    \mathbf{F} = \  \langle x,y,z \rangle 

and we have equations for :math:`x(t), y(t), z(t)`

.. math::

    x = t, \ \ \ \ y = t, \ \ \ \ z = 2t^2 

    \frac{d\mathbf{r}}{dt} = \  \langle \frac{dx}{dt},\frac{dy}{dt},\frac{dz}{dt} \rangle 

    = \  \langle 1,1,4t \rangle 

    \int_C \mathbf{F} \cdot dr \int \mathbf{F} \cdot \frac{d\mathbf{r}}{dt} \ dt = \int_C  \langle t,t,2t^2 \rangle \  \cdot  \langle 1,1,4t \rangle dt 

    = \int_C (2t + 8t^3) dt = t^2 + 2t^4 

Evaluate from say, :math:`t=0` to :math:`t=1`

.. math::

    t^2 + 2t^4 = 3 

It doesn't seem complicated at all, once we have the parametric equations.
