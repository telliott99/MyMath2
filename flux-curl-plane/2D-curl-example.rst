.. _2D-curl-example:

############
Curl example
############

Green's Theorem is

.. math::

    \oint_C \mathbf{F} \cdot \mathbf{dr} = \iint\limits_{R}  curl(\mathbf{F}) \ dA
    
The left-hand side can be written as:

.. math::

    = \oint_C M \ dx + N \ dy

and the right-hand side is really just:

.. math::

    = \iint\limits_{R} (N_x - M_y) \ dA 

The theorem can be used for finding area by computing a line integral.  The trick is to imagine an :math:`M` and :math:`N` such that

.. math::

    N_x - M_y = 1 

because then we have

.. math::

    \oint_C M \ dx + N \ dy  = \iint\limits_{R}  \ dA = Area 

An especially common choice is:

.. math::

    M = -\frac{y}{2}, \ \ N = \frac{x}{2} 

So we have that

.. math::

    A = \frac{1}{2} \oint_C x \ dy - y \ dx 

Let's try this out on a circle.  What is the parametrization of :math:`C`?  We need :math:`x` and :math:`y` as functions of :math:`t`:

.. math::

    x = a \ cos \ t 

    dx = -a \ sin \ t  \ dt 

    y = a \ sin \ t 

    dy = a \ cos \ t  \ dt 

    A = \frac{1}{2} \int_{t=0}^{t=2\pi} a^2 cos^2t \ dt + a^2 sin^2t \ dt 

    = \frac{1}{2} \ a^2 \ 2 \pi = \pi a^2 

What about an ellipse?  What is the parametrization of :math:`C`?  We need :math:`x` and :math:`y` as functions of :math:`t`:

.. math::

    x = a \ cos \ t, 

    dx = -a \ sin \ t  \ dt 

    y = b \ sin \ t 

    dy = b \ cos \ t  \ dt 

To see that the above is correct, do this

.. math::

    \frac{x^2}{a^2} + \frac{y^2}{b^2} = cos^2 \ t + sin^2 \ t = 1 

Clearly the formula of an ellipse.  Now plug into the integral

.. math::

    A = \frac{1}{2} \int_{t=0}^{t=2\pi} ab \ cos^2t \ dt + ab \ sin^2t \ dt 

    \frac{1}{2} \ ab \ 2 \pi = \pi ab 

Finally, what seems a very simple example:

the part of the rectangle :math:`[0,1] \times [0,2]` below the line :math:`y=2x`,

is actually complicated because there are three segments of the curve:

.. math::

    y = 2x 

    dy = 2 \ dx 

    A = \frac{1}{2} \oint_C x \ dy - y \ dx  

    C1:  x = 0 \to 1,\  y = 0 

    C2:  x = 1,\  y = 0 \to 2 

    C3:  y = 2x,\  x = 1 \to 0 

    M = -\frac{y}{2}, \ \ N = \frac{x}{2} 

    A_1 = \frac{1}{2} \oint_C x \ dy - y \ dx = \frac{1}{2} \oint_C x \ 0 - 0 \ dx = 0  

    A_2 = \frac{1}{2} \oint_C x \ dy - y \ dx = \frac{1}{2} \oint_C 1 \ dy - y \ 0 = y \bigg |_0^2 = 1  

    A_3 = \frac{1}{2} \oint_C x \ dy - y \ dx = \frac{1}{2} \oint_C x \ 2 \ dx - 2x \ dx = 0  

The total area is just 1.

