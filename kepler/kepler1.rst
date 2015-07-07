.. _kepler1:

#################
Kepler and Newton
#################

This is part one of ten, about deriving Kepler's Laws for planetary motion from Newton's Laws.  In this part, we look at the geometric proof of K2 used by Newton.

.. image:: /figs/newton_area.png
   :scale: 50 %

We diagram the sun :math:`S` and a planet at :math:`A`.  Imagine that the force toward the sun is applied in small increments (no calculus).

For a small interval :math:`\Delta t`, the planet travels from :math:`A` to :math:`B` at constant velocity and if undisturbed, would travel to :math:`C` in the next unit of time.

In the absence of a force, the velocity would be constant and so the length of :math:`AB` is the same as that of :math:`BC`, and since :math:`AB` is on the same line as :math:`BC`, the area of :math:`\triangle ABS` is equal to the area of :math:`\triangle BCS`.

Proof:  draw the vertical line from :math:`S` to the line containing :math:`ABC`.  The area of either triangle is one-half the length of that altitude times the distance, either :math:`AB` or :math:`BC`.  The principle is illustrated in the next figure.

.. image:: /figs/triangles_parallel.png
   :scale: 50 %

Given two parallel lines separated by a distance :math:`h`, pick two points on one line separated by a distance :math:`d` and \emph{any} point on the other line.  The triangles drawn using those points will all have equal area, namely :math:`(1/2)dh`.

Now, suppose the force is applied at :math:`B` along the path :math:`EBS`, directly *toward the sun*.  As a result, the trajectory :math:`BC` is modified by the change in velocity resulting from application of the force. The new path is the additional velocity times :math:`\Delta t`.  Call the length :math:`CD` and add it to :math:`BC` to give the actual trajectory, :math:`BD`.

:math:`CD` is parallel to :math:`SBE`.  Therefore, every point on :math:`CD` has an altitude with respect to :math:`SBE` of the same length.  So any point on :math:`CD` can be used to draw a triangle with the same base :math:`SB` and the result will have the equal area no matter which point is chosen.

.. image:: /figs/newton_area.png
   :scale: 50 %

In particular, the area of :math:`\triangle BDS` is equal to the area of :math:`\triangle BCS`, which was found earlier to be equal to the area of :math:`\triangle ABS`.  Since the two triangles from the actual motion have the same area, the area is constant.
