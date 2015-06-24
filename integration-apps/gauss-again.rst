.. _gauss again:

###########
Gauss again
###########

In this short write-up I want to take a very quick look at double integrals.  The basic principle of calculus of several variables is that we look at the effect of small changes in *one variable at a time*.  So we write

.. math::

    df = \frac{\partial f}{\partial x} dx + \frac{\partial f}{\partial y} dy 

where, for example, :math:`\partial f/\partial x` is the derivative of :math:`f` with respect to :math:`x`, treating :math:`y` as a constant.

For integration, consider a rectangle where :math:`x` varies between :math:`0 \rightarrow 2`, while :math:`y = 0 \rightarrow 3`.  To compute the area of this rectangle, we write

.. math::

    A = \int_{x=0}^{2} \int_{y=0}^{3} \ dy \ dx 

There is no :math:`f(x,y)` inside the integral sign (except implicitly :math:`f(x,y)=1`), and the result will be the area.  In the same way :math:`\int dx = x_f - x_i`, the length of :math:`x`.

To evaluate the integral, look at the part inside, the inner integral

.. math::

    \int_{y=0}^{3} \ dy 

We need a function whose derivative is :math:`dy`, holding :math:`x` constant.  In this case, that's just :math:`y`, evaluated between the limits.  We obtain

.. math::

    \int_{y=0}^{3} \ dy = y \ \bigg |_0^3 = 3 

So we proceed to evaluate the outer integral

.. math::

    A = \int_{x=0}^{2} 3 \ dx = 3 \int_{x=0}^{2} \ dx = 3 \times 2 = 6 

========================
Something more ambitious
========================

Now consider a circle.  We're going to integrate the function :math:`f(x,y) =1` over a circle of radius :math:`R`.  For simplicity, we do only the first quadrant, and multiply at the end by :math:`4`.

.. math::

    A = \int_{x=0}^R \int_{y=0}^{\sqrt{R^2 - x^2}} \ dy \ dx 

Since :math:`y` changes as a function of :math:`x`, we need to account for that.  That's why we have the upper limit on :math:`y`.  The inner integral is easy

.. math::

    \int_{y=0}^{\sqrt{R^2 - x^2}} \ dy = \sqrt{R^2 - x^2} 

But now the outer integral is

.. math::

    A = \int_{x=0}^R \sqrt{R^2 - x^2} \ dx 

This presents a bit of a problem because we don't have the derivative for what's inside the square root.  We continue anyway, with a trig substitution.

.. math::

    x = R \sin \theta 

    dx = R \cos \theta \ d \theta 

    \sqrt{R^2 - x^2} = R \cos \theta 

So the integral is

.. math::

    \int R^2 \cos^2 \theta \ d \theta 

I've done this before.  The answer is

.. math::

    = R^2 \ \frac{1}{2} ( \theta + \sin \theta \cos \theta) 

The really tricky part is the limits.  We could switch back to :math:`x` or we can recognize that when :math:`x=R`, :math:`\sin \theta = 1` and when :math:`x=0`, :math:`\sin \theta = 0` so we evaluate between :math:`\theta = 0 \rightarrow \pi/2`.  That makes :math:`\sin \theta \cos \theta` go away.  The result is just

.. math::

    = R^2 \ \frac{1}{2} (\frac{\pi}{2} ) 

Multiply by :math:`4` to obtain :math:`\pi R^2`.

=============
An easier way
=============

There is another approach, which is the reason for this particular write-up.  The "area element" in 2D using polar coordinates is

.. math::

    dA = r \ dr \ d \theta 

.. image:: /figs/polararea.png
   :scale: 50 %

The figure shows a rationale for this.  :math:`\theta` or :math:`d \theta` is not a length, :math:`r \ d \theta` is a length.  What we're saying is that the area element in the plane is

.. math::

    dA = dy \ dx = r \ dr \ d \theta 

and for any particular region, we can pick the one that's easier.  Clearly, for a circle, the second way is easier.  We set up the integral

.. math::

    A = \int_{\theta = 0}^{2 \pi} \int_{r=0}^{R} r \ dr \ d \theta 

The inner integral is

.. math::

    \int_{r=0}^{R} r \ dr = \frac{r^2}{2} \ \bigg |_{r=0}^{R}  = \frac{R^2}{2} 

The outer integral is

.. math::

    A = \int_{\theta = 0}^{2 \pi} \frac{R^2}{2} \ d \theta = \frac{R^2}{2} \ 2 \pi = \pi R^2  

===========
Application
===========

We can apply what we've learned to the following problem.  In the Gaussian distribution and also in the physics of molecular velocities we run into an integral like

.. math::

    I = \int_{-\infty}^{\infty} e^{-x^2} \ dx 

There is a great solution to this.  Write

.. math::

    I^2 = \int_{-\infty}^{\infty} e^{-x^2} \ dx \int_{-\infty}^{\infty} e^{-y^2} \ dy 

    = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty}  e^{-(x^2 + y^2)} \ dx \ dy 

But we can change this to polar coordinates

.. math::

    = \int_0^{2 \pi} \int_{0}^{\infty} e^{-r^2} \ r \ dr \ d \theta 

The inner integral is just

.. math::

    \int_{0}^{\infty} e^{-r^2} \ r \ dr = -\frac{1}{2}e^{-r^2} \ \bigg |_0^{\infty} = \frac{1}{2}  

So then we have

.. math::

    I^2 = \int_0^{2 \pi} \frac{1}{2} \ d \theta = \pi  

To put this another way

.. math::

    I = \sqrt{\pi} 

    I = \int_{-\infty}^{\infty} e^{-x^2} \ dx = \sqrt{\pi} 
