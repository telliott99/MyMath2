.. _dot-product2:

####################
Vectors and geometry
####################

Using vectors to derive geometric proofs shows some of their power:

.. image:: /figs/inscribed-right-angle.png
   :scale: 50 % 

In the left panel is illustrated the theorem that if we take the endpoints of a diameter of a circle and any point on the circumference but not on the diameter, they form a right triangle.

The setup for the vector proof is shown in the right panel.  It should be obvious why :math:`-\mathbf{a}` is drawn as it is, and the additions should be easy to work out as well, following the tips of the arrows.

If :math:`\mathbf{u}` is the vector on the right-hand side of the figure:

.. math::

    \mathbf{b} + \mathbf{u} = \mathbf{a}
    
    \mathbf{u} = \mathbf{a} - \mathbf{b}

For the other one:

.. math::

    \mathbf{b} + \mathbf{v} = -\mathbf{a}

    \mathbf{v} = -\mathbf{a} - \mathbf{b}
    
    
For the proof, simply compute the dot product:

.. math:: 

    \mathbf{u} \cdot \mathbf{v} = (\mathbf{a} - \mathbf{b}) \cdot (-\mathbf{a} - \mathbf{b})
    
    = - \mathbf{a} \cdot \mathbf{a} - \mathbf{a} \cdot \mathbf{b} + \mathbf{b} \cdot \mathbf{a} + \mathbf{b} \cdot \mathbf{b} 

    = - \mathbf{a} \cdot \mathbf{a} + \mathbf{b} \cdot \mathbf{b}
    
    = - r^2 + r^2 = 0

==============
Strang example
==============

The last example was nice but a bit understated.  Try this one:  consider *any* four-sided figure in space.  The midpoints of the sides *lie in the same plane*, and further, they form a parallelogram.

.. image:: /figs/strang-vector-proof.png
   :scale: 50 % 

From the figure, we have that vector

.. math:: 

    \mathbf{v} = \mathbf{AQ} + \mathbf{QB}
    
    = \frac{1}{2} \mathbf{A} + \frac{1}{2} \mathbf{B}
    
    = \frac{1}{2} (\mathbf{A} + \mathbf{B})
    
    \mathbf{PR} = A + B = 2 \mathbf{v}

The same argument using vector :math:`\mathbf{w}` and point :math:`S`, will give the same result.  Therefore

.. math:: 

    \mathbf{PR} = 2 \mathbf{v} = 2 \mathbf{w}
    
    \mathbf{v} = \mathbf{w}

This completes the proof that the four sided figure with opposite sides the same vector *is* a parallelogram.

==============
Ceva revisited
==============

Ceva's Theorem says that if we start with a triangle and draw the line segments connecting each vertex with the midpoint of the opposite side, the three line segments cross at a single, unique point.  Furthermore, it is possible to show that for any of these line segments, the *centroid* lies one-third of the length from the side, and two-thirds of the length from the vertex.

I'd like to show a proof of this using vectors, which makes everything particularly simple.  As a warmup, let's start by looking at the midpoint of the diagonals for a parallelogram including the triangle of interest.  We will prove that the two diagonals cross at their mid-points (at :math:`P`).

.. image:: /figs/ceva_vec1.png
   :scale: 50 %

by construction:

.. math::

    \mathbf{a} + \mathbf{b} = \mathbf{c} 

    \mathbf{b} + \mathbf{d} = \mathbf{a}
    
    \mathbf{d} = \mathbf{a} - \mathbf{b}   

Let's define :math:`P` as the point we reach by going halfway along :math:`\mathbf{c}`

.. math::

    \mathbf{c} / 2 =  (\mathbf{a} + \mathbf{b})/2 

What we need to show is that if we do

.. math::

    \mathbf{b} + \mathbf{d}/2 

we also arrive at :math:`P`.  

Since :math:`\mathbf{d} = \mathbf{a} - \mathbf{b}`

.. math::

    \mathbf{b} + \mathbf{d}/2 = \mathbf{b} + (\mathbf{a} - \mathbf{b})/2 = (\mathbf{a} + \mathbf{b})/2
    
:math:`\blacksquare`

Vectors make that pretty easy.

Now, here is the triangle with the centroid drawn in:

.. image:: /figs/ceva_vec2.png
   :scale: 50 %

By construction

.. math::

    \mathbf{b} + \mathbf{f} =   \mathbf{a}/2
    
    \mathbf{f} =   \mathbf{a}/2 - \mathbf{b}

and 

.. math::

    \mathbf{a} + \mathbf{e} =  \mathbf{b}/2
    
    \mathbf{e} =   \mathbf{b}/2 - \mathbf{a} 

and 

.. math::

    \mathbf{a} + \mathbf{b} = \mathbf{c}

    \mathbf{g} = \mathbf{c}/2

    \mathbf{b} + \mathbf{d}/2 =  \mathbf{g}

(For the last one, refer back to the first diagram).

Now we explore three paths to move to  :math:`Q`.

It makes it a little easier when we know that :math:`Q` is two-thirds of the way along each interior line segment.

Starting from :math:`O`:

.. math::

    \frac{2}{3} \mathbf{g} = \frac{2}{3} \ \frac{1}{2} \mathbf{c} = \mathbf{c}/3 = (\mathbf{a} + \mathbf{b})/3 

from :math:`S`:

.. math::

    \mathbf{b} + \frac{2}{3} \mathbf{f} = \mathbf{b} +  \frac{2}{3}( \mathbf{a}/2 - \mathbf{b}) =  (\mathbf{a} + \mathbf{b})/3 

or from :math:`T`:

.. math::

    \mathbf{a} + \frac{2}{3} \ \mathbf{e} = \mathbf{a} + \frac{2}{3} \ (\mathbf{b}/2 - \mathbf{a}) =  (\mathbf{a} + \mathbf{b})/3

Since all three paths are equal (in the vector sense), we arrive at the same point by each of the three paths, proving the theorem.

How would we find the factor of :math:`2/3` if we didn't already know?  Call that unknown factor :math:`r`.  If we can solve for :math:`r`, then the solution exists.

.. math::

    r \ (\mathbf{a} + \mathbf{b})/2 + (1-r) \ \mathbf{e} = \mathbf{b} / 2 
    
Since

.. math::

    \mathbf{e} =  \mathbf{b}/2 - \mathbf{a} 

    r \ (\mathbf{a} + \mathbf{b})/2 + (1-r) \ (\mathbf{b}/2 - \mathbf{a}) = \mathbf{b} / 2 

Expand:

.. math::

    r (\mathbf{a}/2) + r (\mathbf{b}/2) + \mathbf{b}/2 - r (\mathbf{b}/2) -  \mathbf{a} + r  \mathbf{a} =  \mathbf{b}/2 

    r (\mathbf{a}/2)  + \mathbf{b}/2 -  \mathbf{a} + r  \mathbf{a} =  \mathbf{b}/2 
    
    r (\mathbf{a}/2) -  \mathbf{a} + r  \mathbf{a} =  0 

    (3/2)r \mathbf{a} - \mathbf{a} = 0 

    (3/2)r  = 1 

    r = 2/3 

  