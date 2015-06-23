.. _law-of-cosines:

##############
Law of Cosines
##############

Here, we'll work through an algebraic proof of the law of cosines.  In the triangle below, :math:`A`, :math:`B`, and :math:`C` are the angles, with side lengths :math:`a`, :math:`b`, and :math:`c`.

.. image:: /figs/triangle.png
   :scale: 50 %

An altitude has been drawn from the vertex with angle :math:`C` to side :math:`c` opposite.  The altitude is perpendicular to the side :math:`c`, which is thereby divided into lengths :math:`d` and :math:`e`.

The large triangle and the two smaller ones made from it are all similar to each other.  This is easily proven using complementary angles of a right triangle.

We'll use these four facts

.. math::

    c = d + e

    a^2 = e^2 + h^2

    b^2 = d^2 + h^2

    d = b \cos A

Start with

.. math::

    a^2 = e^2 + h^2

Knowing that

.. math::

    b^2 = d^2 + h^2

    h^2 = b^2 - d^2

substitute for :math:`h^2`

.. math::

    a^2 = e^2 + b^2 - d^2

Since :math:`e = c - d`, substitute for :math:`e^2`

.. math::

    a^2 = (c-d)^2 + b^2 - d^2

    = c^2 -2cd + d^2 + b^2 - d^2

    = b^2 + c^2 -2cd

Finally, substitute for :math:`d` knowing that :math:`d = b \cos A`

.. math::

    a^2 = b^2 + c^2 -2bc \cos A

QED.

This is the Law of Cosines.

Notice that if :math:`A = 90^\circ`, :math:`d=0` and :math:`cos A = 0`, and this becomes the Pythagorean Theorem.

Another way, which is slightly shorter:

.. image:: /figs/triangle.png
   :scale: 50 %

.. math::

    d = b \cos A

    e = c - d = c - b \cos A

    h = b \sin A

So, using Pythagoras

.. math::

    a^2 = h^2 + e^2

    = b^2 \sin^2 A + c^2 - 2 bc \cos A + b^2 \cos^2 A

    = b^2 + c^2 - 2bc \cos A
