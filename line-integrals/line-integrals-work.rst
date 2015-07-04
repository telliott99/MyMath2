.. _line-integrals-work:

#######################
Line integrals for work
#######################

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

    \mathbf{F} = \  \langle M,N \rangle 

then this becomes

.. math::

    \int_C  \  \langle M,N \rangle \ \cdot \  \langle \frac{dx}{dt},\frac{dy}{dt} \rangle \ dt 

We could even write this

.. math::

    \int_C  M \ dx + N \ dy = \int_C \mathbf{F} \cdot d\mathbf{r}

That would be a good one to remember.

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

and since :math:`\mathbf{F} = \  \langle x,y \rangle`, :math:`M = x = t`.

.. math::

    \int_C  \  \langle M,N \rangle \ \cdot \  \langle \frac{dx}{dt},\frac{dy}{dt} \rangle \ dt = \int M dt 

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

That's interesting, why is the total work zero?  It turns out to be because our force :math:`\mathbf{F} = \  \langle x,y \rangle` is the gradient of a potential function.

.. math::

    \mathbf{F} = \nabla \mathbf{f} 

where

.. math::

    \nabla = \  \langle  \ \frac{\partial }{\partial  x},\frac{\partial }{\partial  y},\frac{\partial }{\partial  z}  \rangle 

Can we guess what function? Sure!

.. math::

    f(x,y) = \frac{1}{2}x^2 + \frac{1}{2}y^2 

That gives the correct values for the components of :math:`\mathbf{F}`

.. math::

    \mathbf{F} = \nabla \mathbf{f} = \nabla ( \frac{1}{2}x^2 + \frac{1}{2}y^2) = \  \langle f_x,f_y \rangle \ = \  \langle x,y \rangle 

and since

.. math::

    \hat{\mathbf{T}} \ ds = (dx\ \hat{\mathbf{i}} + dy\ \hat{\mathbf{j}}) 

Then, at least in the case where this gradient condition holds, we have

.. math::

    \int_C \mathbf{F} \cdot  \hat{\mathbf{T}} \ ds  = \  \langle f_x,f_y \rangle \  \cdot  (dx\ \hat{\mathbf{i}} + dy\ \hat{\mathbf{j}})  

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

:math:`C` is a sector of the unit circle between :math:`0  \langle = \theta  \langle = \pi/4`.  We break the curve up into 3 parts.

:math:`C_1`, from :math:`(0,0)` to :math:`(0,1)`.  As before, notice that :math:`y=0`, so :math:`dy=0` and

.. math::

    \int_C y \ dx + x \ dy = 0 

Also, notice that :math:`\mathbf{F}` is :math:` \langle 0,x \rangle`, so :math:`\mathbf{F} \perp d\mathbf{r}` and then  :math:`\mathbf{F} \cdot d\mathbf{r} = 0`.

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

    F = \nabla f = \  \langle  \ f_x,f_y \  \rangle \ = \  \langle  \ y,x \  \rangle 

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

    = \int_C \  \langle  \sin t + 1, \cos t  \rangle \  \cdot \  \langle  -\sin t , \cos t \rangle \ dt 

    = \int_C \ - \sin^2 t - \sin t + \cos^2 t \ dt 

    = \int_C \cos 2t - \sin t \ dt 

    = \frac{1}{2} \sin 2t + \cos t   \ \bigg|_0^{\pi} = -2 

Another one:  determine if :math:`\mathbf{F} = \  \langle z,2yz,x+y^2 \rangle` is conservative.  There is a general method for this, but let's see if we can guess.

Since :math:`f_x = z`, the function is :math:`f = xz + ..`

Since :math:`f_y = 2yz`, the function is :math:`f = y^2z + ..`

Since :math:`f_z = x + y^2`, the function is :math:`f = xz + y^2z + ..`

We have the terms we need for the partial derivatives to work out.

.. math::

    f = xz + y^2z + \text{constant}
