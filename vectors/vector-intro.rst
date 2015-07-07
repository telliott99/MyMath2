.. _vector-intro:

#######
Vectors
#######

I want to emphasize a few useful properties of and operations on vectors in two- and three-dimensional space.  I assume that you have already encountered vectors before, so they are not totally new.  

A vector is a mathematical object that has both magnitude and direction.  For example, in the standard 2D-coordinate system, the vector :math:`\langle 1,2 \rangle` goes from the origin one unit in the :math:`x`-direction and two units in the :math:`y`-direction.

So, a vector has one property of a line, slope, but the fixed magnitude means that a vector does not extend to infinity as a line does.

Also, by convention we allow vectors to move about in space.

We mean that two vectors of the same length, and pointing in the same direction are the same object, regardless of where they are located in space.  (Some physics problems don't allow this, but in math it's the usual case).  

So if we have the vector :math:`\mathbf{u} = \langle 1,1 \rangle` starting at the origin :math:`(0,0)` and ending at the point :math:`(1,1)`, and compare it to a second vector :math:`\mathbf{v}` that starts from :math:`(2,0)` and ends at :math:`(3,1)`, that's the same vector.

As you may guess, with two points :math:`(x_1,y_1)` and :math:`(x_2,y_2)`, the vector that connects them is 

.. math::

    \mathbf{u} = \langle x_2-x_1,y_2-y_1 \rangle

If we do the subtraction in reverse we have 

.. math::

    \mathbf{v} = \langle x_1-x_2,y_1-y_2 \rangle

    \mathbf{u} = - \mathbf{v}

In print, vectors are often marked with bold font (:math:`\mathbf{v}`) or with an arrow overhead to show what kind of object they are.

From one point of view, a vector is simply an ordered collection of numbers

.. math::

    \mathbf{v} =  \langle v_1, v_2, \cdots \ a_n \rangle

where :math:`n` could be very large, even infinite.  However, a lot of work is done in two or three dimensions (officially :math:`\mathbb{R}^2` and :math:`\mathbb{R}^3`), and the principles developed there carry over nicely into :math:`n`-dimensional space.  So let's start by thinking about a two-dimensional vector

.. math::

    \mathbf{v} =  \langle v_1, v_2 \rangle

==========
Arithmetic
==========

Vectors can be added together, and subtracted as well.  They can also be multiplied by a real number.  When we're talking about vectors we usually call a plain real number a *scalar*.  Vectors can also multiply vectors, we'll get to that in later sections.

Addition and subtraction are done as you'd expect, working on each component in turn:

.. math::

    \mathbf{u} = \langle u_1, u_2 \rangle

    \mathbf{v} = \langle v_1, v_2 \rangle
    
    \mathbf{u} + \mathbf{v} = \langle u_1 + v_1, u_2 + v_2 \rangle

    \mathbf{u} - \mathbf{v} = \langle u_1 - v_1, u_2 - v_2 \rangle

Multiplication by a scalar :math:`c` is just:

.. math::

    c \ \mathbf{u} = \langle c u_1, c u_2 \rangle

Suppose :math:`c=-1`:

.. math::

    (-1) \ \mathbf{u} = - \mathbf{u} = (-1) (\langle u_1, u_2 \rangle) = \langle -u_1, -u_2 \rangle

As expected:

.. math::

    \mathbf{u} - \mathbf{u} = \mathbf{0}

Note that this is the zero *vector*

.. math::

    \mathbf{0} = \langle 0, 0 \rangle

If a triangle is drawn with one vertex at the origin and :math:`u` and :math:`v` as the two sides extending away from the origin, then third side can also be described in vector language.  

If :math:`w` extends from the point :math:`u_1,u_2` *toward* :math:`v_1,v_2`, then

.. math::

    \mathbf{u} + \mathbf{w} = \mathbf{v}

and

.. math::

    \mathbf{u} = \mathbf{v} - \mathbf{w}

============
Unit vectors
============

As I've suggested, the vector :math:`\mathbf{v}` can be thought of as an arrow that goes from the origin to the point :math:`(v_1,v_2)`.  It has both length and direction.  Its length is given (from the Pythagorean Theorem) by

.. math::

    |\mathbf{v}|^2 = v_1^2 + v_2^2

    v = |\mathbf{v}| = \sqrt{v_1^2 + v_2^2}

Since this :math:`v` is just a number, we do not use the vector symbol or bold it.

Its direction is

.. math::

    \frac{v_2}{v_1} = tan \ \theta, \ \ \ \  \theta = tan^{-1}(\frac{v_2}{v_1})

where :math:`\theta` is the angle the vector makes (going counter-clockwise) with the positive :math:`x`-axis.
Any vector can be converted into a *unit vector*, a vector of length one, by dividing by its length.  For example if :math:`\mathbf{v} = \langle 1,2\rangle` then 

.. math::

    v = \sqrt{v_1^2 + v_2^2} = \sqrt{5}

    \mathbf{\hat{v}} =  \frac{1}{v}\ \mathbf{v} = \ \langle\frac{1}{\sqrt{5}}, \frac{2}{\sqrt{5}}\rangle

is a unit vector pointing in the same direction as :math:`\mathbf{v}`.  The "hat" symbol indicates a unit vector:  :math:`\mathbf{\hat{v}}`.

The standard unit vectors (sometimes called a *basis*) are 

.. math::

    \mathbf{\hat{i}} = \langle 1,0 \rangle
    
    \mathbf{\hat{j}} = \langle 0,1 \rangle

The line through the origin with slope :math:`m = v_2/v_1` and equation

.. math::

    y = mx

can be thought of as being the extension of vector :math:`\mathbf{v}` obtained by multiplying some :math:`t` times :math:`\mathbf{v}` for all :math:`t \in \mathbb{R}`.

.. math::

    L = t \mathbf{v} \ \ \forall \ t \in \mathbb{R}