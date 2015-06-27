.. _line-integrals:

##############
Line integrals
##############

A straightforward application of a line integral is to find the length of a curve.  A more sophisticated one yields the work done when moving along a curve, and there are certainly others.

The basic formula can be derived by doing algebra with differentials.  Think of a small element of the path of the curve, :math:`ds`, as a right triangle with side lengths :math:`dx` and :math:`dy`.  Then

.. math::

    ds^2 = dx^2 + dy^2 

We "divide and multiply" on the right by :math:`dx^2` to give

.. math::

    ds^2 = \frac{1}{dx^2} \ (dx^2 + dy^2) dx^2

    ds^2 = [1 + \frac{dy^2}{dx^2}] \ dx^2 

then take the square root

.. math::

    ds = \sqrt{1 + (\frac{dy}{dx})^2} \ dx 

    ds = \sqrt{1 + (y')^2} \ dx 

In many cases :math:`x` and :math:`y` will be parametric equations (functions of a parameter like :math:`t`), but they don't have to be.

=========
Example 0
=========

Here is one where we already know the answer:  the arc length along the boundary of the circle of radius :math:`R` in the first quadrant.  Again, the formula is

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

This can be solved by a trig substitution:

.. math::

    x = R \sin t 

    dx = R \cos t \ dt 

    \sqrt{R^2 - x^2} = R \cos t 

So we have

.. math::

    = R \int \frac{1}{R \cos t} R \cos t \ dt = R^2 t 

The slightly tricky part is the limits on :math:`t`.  The lower limit was :math:`x=0`, so now we need :math:`R \sin t = 0`, so :math:`t=0`.  And the upper limit was :math:`x=R`, so now we need :math:`R \sin t = R` so :math:`t = \pi/2`.  The integral is :math:`\pi R/2` and the whole circumference is :math:`4` times that or :math:`C = 2 \pi R`.

Another, simpler way to do this calculation is to use the parametrized circle (:math:`x = \cos \theta, y = \sin \theta`).  Go back to the original definition of the element of arc :math:`ds`:

.. math::

    ds^2 = dx^2 + dy^2 

    L = \int ds = \int \sqrt{dx^2 + dy^2} 

    = \int \sqrt{\cos^2 \theta + \sin^2 \theta} \ d \theta 

    = \int \ d \theta 

Here, we can just go all the way around the circle from :math:`\theta = 0 \Rightarrow 2 \pi`.  And for a circle of radius :math:`a` we have :math:`a \cos \theta` and :math:`a \sin \theta` which gives a factor of :math:`a^2` under the square root, yielding an extra factor of :math:`a` in the end.

=========
Example 1
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
Example 2
=========

Most commonly, however, we have :math:`x` and :math:`y` as functions of a parameter :math:`t`.  Also we may have a vector field :math:`\mathbf{F}` where

.. math::

    \mathbf{F} = \ <M,N> 

or

.. math::

    \mathbf{F} = \ <P,Q,R> 

and we are interested in the integral along the curve (for the work done by :math:`\mathbf{F}`):

.. math::

    \int_C \mathbf{F} \cdot d\mathbf{r} = \int_C \mathbf{F} \cdot \hat{\mathbf{T}} ds 

    = \int_C P \ dx + Q \ dy + R \ dz 

This last part probably seems like a magic trick.  We'll see how it's done in the next section.

Here I would like to show how we evaluate it.  The crucial insight is provided by parametrization of the curve.  That gives us a function of a single variable.  Suppose

.. math::

    \mathbf{F} = \ <x,y,z> 

and we have equations for :math:`x(t), y(t), z(t)`

.. math::

    x = t, \ \ \ \ y = t, \ \ \ \ z = 2t^2 

    \frac{d\mathbf{r}}{dt} = \ <\frac{dx}{dt},\frac{dy}{dt},\frac{dz}{dt}> 

    = \ <1,1,4t> 

    \int_C \mathbf{F} \cdot dr \int \mathbf{F} \cdot \frac{d\mathbf{r}}{dt} \ dt = \int_C <t,t,2t^2> \  \cdot <1,1,4t> dt 

    = \int_C (2t + 8t^3) dt = t^2 + 2t^4 

Evaluate from say, :math:`t=0` to :math:`t=1`

.. math::

    t^2 + 2t^4 = 3 

It doesn't seem complicated at all, once we have the parametric equations.

====
Work
====

The basic line integral is something like this one for work

.. math::

    W = \int_C \mathbf{F} \cdot d\mathbf{r} 

We have a curve :math:`C` made up of lots of little pieces :math:`d\mathbf{r}`.  For each piece, we compute the dot product with the force :math:`\mathbf{F}`, multiplying by the component of the force that is in the same direction as we're headed.

As before, it makes great sense symbolically, but how to compute it?  To start with do

.. math::

    d\mathbf{r} = \hat{\mathbf{T}} \ ds 

where :math:`\hat{\mathbf{T}}` is the unit vector in the direction of :math:`d\mathbf{r}` and :math:`ds` is the magnitude of :math:`d\mathbf{r}` (that is, the speed).

Moreover, notice that

.. math::

    \frac{d\mathbf{r}}{dt} = \mathbf{v} = \hat{\mathbf{T}} \ \frac{ds}{dt} 

so

.. math::

    \int_C \mathbf{F} \cdot d\mathbf{r} =  \int_C \mathbf{F} \cdot \mathbf{v} \ dt =  \int_C \mathbf{F} \cdot \mathbf{T}\ \frac{ds}{dt} \ dt  

If :math:`\mathbf{F}` has components

.. math::

    \mathbf{F} = \ <M,N> 

then this becomes

.. math::

    \int_C  \ <M,N> \ \cdot \ <\frac{dx}{dt},\frac{dy}{dt}> \ dt 

We could even write this

.. math::

    \int_C  M \ dx + N \ dy 

This is a useful mnemonic, but remember that this is a single integral, and we can't just do :math:`dx` and :math:`dy` separately.  We need a single variable and :math:`t`, the parameter for the curve :math:`C`, comes to the rescue.  (Either that or :math:`y=f(x)`).  We must get all these in terms of :math:`t`.  Then it's OK.  Also, it may be necessary to break the curve up into pieces.

Suppose :math:`C` is the unit square and

.. math::

    \mathbf{F} = \langle x,y \rangle

For the first leg we have :math:`y=0` and :math:`x=0 \rightarrow 1`.  So parametrize :math:`x` using :math:`t` by setting :math:`x=t` and let :math:`t=0 \rightarrow 1`.  Now

.. math::

    dx/dt = 1 

and

.. math::

    dy/dt=0 

and since :math:`\mathbf{F} = \ <x,y>`, :math:`M = x = t`.

.. math::

    \int_C  \ <M,N> \ \cdot \ <\frac{dx}{dt},\frac{dy}{dt}> \ dt = \int M dt 

    = \int t \ dt \ \bigg|_0^1 

    = \frac{1}{2} 

In a similar way, on the second leg (up to :math:`(1,1)`)

.. math::

    dx/dt=0 

and

.. math::

    dy/dt=1 

and we have exactly the same integral.

For the third and fourth legs, we get a minus sign (because :math:`x` and :math:`y` are equal to minus :math:`t`), but again the absolute value of the integral is :math:`\frac{1}{2}`, and in the end the total work is 0.

That's interesting, why is the total work zero?  It turns out to be because our force :math:`\mathbf{F} = \ <x,y>` is the gradient of a potential function.

.. math::

    \mathbf{F} = \nabla \mathbf{f} 

where

.. math::

    \nabla = \ < \ \frac{\partial }{\partial  x},\frac{\partial }{\partial  y},\frac{\partial }{\partial  z} > 

Can we guess what function? Sure!

.. math::

    f(x,y) = \frac{1}{2}x^2 + \frac{1}{2}y^2 

That gives the correct values for the components of :math:`\mathbf{F}`

.. math::

    \mathbf{F} = \nabla \mathbf{f} = \nabla ( \frac{1}{2}x^2 + \frac{1}{2}y^2) = \ <f_x,f_y> \ = \ <x,y> 

and since

.. math::

    \hat{\mathbf{T}} \ ds = (dx\ \hat{\mathbf{i}} + dy\ \hat{\mathbf{j}}) 

Then, at least in the case where this gradient condition holds, we have

.. math::

    \int_C \mathbf{F} \cdot  \hat{\mathbf{T}} \ ds  = \ <f_x,f_y> \  \cdot  (dx\ \hat{\mathbf{i}} + dy\ \hat{\mathbf{j}})  

written with the "del" notation

.. math::

    = (\frac{\partial f}{\partial  x} \hat{\mathbf{i}} + \frac{\partial f}{\partial  y} \hat{\mathbf{j}}) \cdot (dx\ \hat{\mathbf{i}} + dy\ \hat{\mathbf{j}}) 

    = \frac{\partial f}{\partial  x} \ dx + \frac{\partial f}{\partial  y} \ dy 

    = df 

===============
Another example
===============

Suppose :math:`\mathbf{F}` is :math:`\langle y,x \rangle` and we want

.. math::

    \int_C \mathbf{F} \cdot  \hat{\mathbf{T}} \ ds 

    = \int_C y \ dx + x \ dy 

:math:`C` is a sector of the unit circle between :math:`0 <= \theta <= \pi/4`.  We break the curve up into 3 parts.

:math:`C_1`, from :math:`(0,0)` to :math:`(0,1)`.  As before, notice that :math:`y=0`, so :math:`dy=0` and

.. math::

    \int_C y \ dx + x \ dy = 0 

Also, notice that :math:`\mathbf{F}` is :math:`<0,x>`, so :math:`\mathbf{F} \perp d\mathbf{r}` and then  :math:`\mathbf{F} \cdot d\mathbf{r} = 0`.

For :math:`C_2` from :math:`(0,1)` to :math:`(1/\sqrt{2},1/\sqrt{2})`  Here, we're on the unit circle.  It's natural to change variables:

.. math::

    x = \cos \ \theta 

    dx = -sin \ \theta \ d \theta 

    y = \sin \ \theta 

    dy = \cos \ \theta \ d \theta 

    \int_C y \ dx + x \ dy  

    = \int_C -\sin^2 \theta \ d \theta + \cos^2 \theta \ d \theta 

    = \int_C \cos \ 2 \theta \ d \theta 

    = \frac{1}{2} \sin \ 2 \theta \ \bigg|_0^{\pi/4} 

    = \frac{1}{2} 

For :math:`C_2` from :math:`(1/\sqrt{2},1/\sqrt{2})` back to :math:`(0,0`, we could do :math:`x=y=t`, but we don't need :math:`t`, instead just use :math:`x=y` and :math:`dx=dy` then

.. math::

    \int_C y \ dx + x \ dy  

    2 \int_C x \ dx 

    = x^2  \ \bigg|_{1/\sqrt{2}}^0 

    = \frac{1}{2} 

So, once again, the total integral is :math:`0`.

And the reason is that :math:`\mathbf{F}` is (again) the gradient (:math:`\nabla`) of a potential function.  By guessing, we obtain this formula for the potential:

.. math::

    f(x,y) = xy 

    F = \nabla f = \ < \ f_x,f_y \ > \ = \ < \ y,x \ > 

The fundamental theorem of calculus for line integrals:

.. math::

    \int_C \nabla f \cdot d \mathbf{r} =   f(P1) - f(P2) 

The example is a closed curve (P1 = P2), so of course it's just 0.  

But we can also do each part separately using the method.  We get :math:`f(x,y) = (1/\sqrt{2} \times 1/\sqrt{2}) = 1/2` along :math:`C_2` (starting from :math:`0` at :math:`C_1`), and of course, minus that along :math:`C_3`, back to :math:`(0,0)`.

In the case where :math:`\mathbf{F}` is the gradient (:math:`\nabla`) of a potential function

.. math::

    \mathbf{F} \cdot \hat{\mathbf{T}} ds = (f_x \ \hat{\mathbf{i}} + f_y \ \hat{\mathbf{j}}) \cdot (dx \ \hat{\mathbf{i}} + dy \ \hat{\mathbf{j}} ) 

\vspace{2 mm}

====
More
====

Here are two more examples, from the OSU site:

- www.math.oregonstate.edu/home/programs/undergrad/

- CalculusQuestStudyGuides/vcalc/conserve/conserve.html


If :math:`\mathbf{F}` is the gradient of a function, then by FTC for line integrals

.. math::

    \int_C \nabla f \cdot d \mathbf{r} = \int_C \mathbf{F} \cdot d \mathbf{r} =    f(P1) - f(P2) 

For example, suppose :math:`f(x,y) = xy + x` and C is the top half of the unit circle (starting from :math:`\theta=0`), then

.. math::

    \mathbf{F} = \nabla f = \langle f_x, f_y \rangle \  = \ \langle y+1,x \rangle 

Parameterize the curve :math:`C` by

.. math::

    x=\cos t, \ \ y = \sin t 

:math:`t = 0 \rightarrow t = \pi`.

.. math::

    dx = - \sin t \ dt, \ \ dy = \cos t \ dt 

    \int_C \nabla f \cdot d \mathbf{r} = (f_x \ \hat{\mathbf{i}} + f_y \ \hat{\mathbf{j}}) \cdot (dx \ \hat{\mathbf{i}} + dy \ \hat{\mathbf{j}} ) 

    = \int_C \ < \sin t + 1, \cos t > \  \cdot \ < -\sin t , \cos t> \ dt 

    = \int_C \ - \sin^2 t - \sin t + \cos^2 t \ dt 

    = \int_C \cos 2t - \sin t \ dt 

    = \frac{1}{2} \sin 2t + \cos t   \ \bigg|_0^{\pi} = -2 

Another one:  determine if :math:`\mathbf{F} = \ <z,2yz,x+y^2>` is conservative.  There is a general method for this, but let's see if we can guess.

Since :math:`f_x = z`, the function is :math:`f = xz + ..`

Since :math:`f_y = 2yz`, the function is :math:`f = y^2z + ..`

Since :math:`f_z = x + y^2`, the function is :math:`f = xz + y^2z + ..`

We have the terms we need for the partial derivatives to work out.

.. math::

    f = xz + y^2z + \text{constant}
