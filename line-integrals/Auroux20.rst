.. _Auroux 20:

#########
Auroux 20
#########

At the end, we'll get to the fundamental theorem of calculus for line integrals, which is that

.. math::

    \int_{P1}^{P2} \nabla \mathbf{F} \cdot d\mathbf{r} = f_{P2} - f_{P1} \iff \mathbf{F} = \nabla f 

    \int_{P1}^{P2} f_x \ dx + f_y \ dy = f(P2) - f(P1) 

+++++++++
Example 1
+++++++++

We usually have :math:`x` and :math:`y` as functions of a parameter :math:`t`.  Also we will have a vector field :math:`F` where

.. math::

    F = \ \langle M,N\rangle 

or in :math:`\mathbb{R^3}`:

.. math::

    F = \ \langle P,Q,R\rangle  

and we are interested in the integral along the curve

.. math::

    \int_C F \cdot dr = \int_C F \cdot T ds = \int_C P dx + Q dy + R dz 

Suppose

.. math::

    F = \ \langle x,y,z\rangle  

and we have equations for :math:`x(t), y(t), z(t)`

.. math::

    x = t, \ \ \ \ y = t, \ \ \ \ z = 2t^2 

    \frac{dr}{dt} = \ \langle \frac{dx}{dt},\frac{dy}{dt},\frac{dz}{dt}\rangle  = \ \langle 1,1,4t\rangle  

    \int_C F \cdot dr = \int_C \langle t,t,2t^2\rangle  \  \cdot \langle 1,1,4t\rangle  dt 
    
    = \int_C (2t + 8t^3) dt 
    
    = t^2 + 2t^4 

Evaluate from say, :math:`t=0` to :math:`t=1`

.. math::

    t^2 + 2t^4 = 3 

+++++++++
Example 2
+++++++++

Suppose F is :math:`\langle y,x\rangle` and C is a sector of the unit circle between :math:`0 \le \theta \le \frac{\pi}{4}`, so that we start at the origin and go out along the radius, along the circle, and then come back to the origin.  Break the curve up into three parts.

.. math::

    \int_{C1} = \int_0^1 M \ dx + N \ dy  = \int_0^1 y \ dx + x \ dy  = 0 

Notice that both :math:`y=0` and :math:`dy = 0`, since we're going out along y = 0.  Also, notice that F is :math:`\langle 0,x \rangle`, so that :math:`F \perp dr` and so :math:`F \cdot dr = 0`.

For C2 we are on the unit circle going from :math:`(0,1)` to :math:`(\frac{1}{\sqrt{2}},\frac{1}{\sqrt{2}})`.

.. math::

    \int_C y \ dx + x \ dy 

The natural thing to do here is to change variables

.. math::

    x = \cos \theta , \ \ \ \ y = \sin \theta 

    dx = -\sin \theta, \ \ \ \ dy = \cos \theta 

    \int_{C2} y \ dx + x \ dy = \int_{C2} (-\sin^2 \theta + \cos^2 \theta) \  d \theta 

Perhaps you can recognize the double-angle formula?

.. math::

    = \int_{C2} \cos 2\theta \ d \theta = \frac{1}{2} \sin 2 \theta

    = [ \ \frac{1}{2} \sin 2 \theta \ ] \bigg |_0^{\pi/4} =  \frac{1}{2} 

For C3 we are moving back along the radius from :math:`(\frac{1}{\sqrt{2}},\frac{1}{\sqrt{2}})` to :math:`(0,0)`

.. math::

    \int_C y \ dx + x \ dy 

Notice that we are moving along the line :math:`y=x` so :math:`dy = dx` and

.. math::

    \int_C y \ dx + x \ dy =  2  \int_C x \ dx = x^2 \  \bigg |_\frac{1}{\sqrt{2}}^0 = -\frac{1}{2}  

The total integral is the sum which is :math:`0 + \frac{1}{2} - \frac{1}{2} = 0`.  The reason for this special result is that \mathbf{F} is the gradient of a potential function.  We are just going to guess what that function is

.. math::

    f(x,y) = xy 

The gradient of f is

.. math::

    \nabla f  = \ \langle f_x,f_y \rangle \ 
    
    = \  \langle y,x \rangle = \mathbf{F}

The fundamental theorem of calculus for line integrals with a conservative vector field is

.. math::

    \int_C F \cdot dr = f(P_1) - f(P_2) 

The example is a closed curve :math:` (P_1 = P_2)` so the difference is just 0.

The question you might ask is how do we know that :math:`f(x,y) = xy` is a potential function?  Answer:  a conservative vector field has zero curl:  :math:`N_x = M_y`.

To restate

.. math::

    \int_{P1}^{P2} \nabla \mathbf{F} \cdot d\mathbf{r} = f_{P2} - f_{P1} \iff \mathbf{F} = \nabla f 

Here's a proof

.. math::

    \int_C \nabla \mathbf{F} \cdot d\mathbf{r} = \int_C f_x \ dx + f_y \ dy 

    x = x(t), \ \ dx = x'(t) \ dt 

    y = y(t), \ \ dy = y'(t) \ dt 

    \int_{t_0}^{t_1} (f_x \ \frac{dx}{dt} + f_y \ \frac{dy}{dt}) \ dt 
    
    = \int_{t_0}^{t_1} \frac{df}{dt} \ dt 
    
    = \int_{t_0}^{t_1} df = f(t_1) = f(t_0) 

Remember the field in example 2:  :math:`\langle y,x \rangle`.  Can we think of a function :math:`f` whose :math:`df/dx = y` and :math:`df/dy = x`?  How about :math:`f=xy`!

Repeat:

Section 1:

.. math::

    P_0 = (0,0); \ \  P_1 = (1,0); \ \  f(P_1) - f(P_0) = 0 - 0 = 0 

Section 2:

.. math::

    P_0 = (1,0); \ \  P_1 = (\frac{1}{\sqrt{2}},\frac{1}{\sqrt{2}}); \ \  f(P_1) - f(P_0) = \frac{1}{2} - 0 = \frac{1}{2} 

Section 3:

.. math::

    P_0 = (\frac{1}{\sqrt{2}},\frac{1}{\sqrt{2}}); \ \  P_1 = (0,0); \ \  f(P_1) - f(P_0) = 0 - \frac{1}{2} = - \frac{1}{2} 

And the sum is, of course, 0.

Consider :math:`\mathbf{F} = \langle -y,x \rangle`.  :math:`\mathbf{F}` is not the gradient of some function, because :math:`N_x \ne M_y`.

Very important:  

.. math::

    \text{Curl} \ (\mathbf{F}) = N_x - M_y 
    
For a conservative vector field, the curl is zero.

- if :math:`\mathbf{F}` is conservative, :math:`\int_C \mathbf{F} \cdot d\mathbf{r} = 0` for all closed paths

- :math:`\int_C \mathbf{F} \cdot d\mathbf{r}` is path-independent

- :math:`\mathbf{F}=\nabla f` and

- :math:`M \ dx + N \ dy` is an *exact* differential:  :math:`df = f_x \ dx + f_y \ dy`.
