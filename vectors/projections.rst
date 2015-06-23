.. _projections:

##################
Vector projections
##################

Consider two vectors :math:`\mathbf{a}` and :math:`\mathbf{b}`, which are drawn starting from the same point with an angle :math:`\theta` between them.  In general, the two vectors  :math:`\mathbf{a}` and :math:`\mathbf{b}` are not unit vectors.

The axes have been drawn so that  :math:`\mathbf{a}` is horizontal.

.. image:: /figs/dot3.png
   :scale: 50 % 

We are interested in the projection of :math:`\mathbf{b}` on :math:`\mathbf{a}`.  We drop a perpendicular line segment from the end of :math:`\mathbf{b}` onto :math:`\mathbf{a}`.  This gives two new vectors, the projection :math:`\mathbf{p}` which is parallel to :math:`\mathbf{a}`, and another vector :math:`\mathbf{e}` such that 

.. math::

    \mathbf{p}  +  \mathbf{e} =  \mathbf{b}

Strang calls :math:`\mathbf{e}` the *error* vector, hence the nomenclature.

How to calculate :math:`\mathbf{p}`   and :math:`\mathbf{e}`?  We use the fact that :math:`\mathbf{p}` and :math:`\mathbf{e}` are perpendicular.  Thus:

.. math::

    \mathbf{e} \cdot \mathbf{p} = \mathbf{p} \cdot \mathbf{e} = 0

So starting from

.. math::

    \mathbf{p}  +  \mathbf{e} =  \mathbf{b}
    
    \mathbf{p} \cdot \mathbf{p}  +  \mathbf{e}  \cdot \mathbf{p}  =  \mathbf{b}  \cdot \mathbf{p}
    
    \mathbf{p} \cdot \mathbf{p}  =  \mathbf{b}  \cdot \mathbf{p}

Here we have used the fact that the dot product is distributive over vector addition (:ref:`here <dot-product>`)

Since the projection :math:`\mathbf{p} = t \mathbf{a}`, where :math:`t` is some constant

.. math::

    t\mathbf{a} \cdot t\mathbf{a}  =  \mathbf{b}  \cdot t \mathbf{a}

factor out one :math:`t`

.. math::

    t\mathbf{a} \cdot \mathbf{a}  =  \mathbf{b}  \cdot \mathbf{a}
    
    t = \frac{\mathbf{b}  \cdot \mathbf{a} }{\mathbf{a}  \cdot \mathbf{a} }

Furthermore, if :math:`\mathbf{a}` has been re-scaled to be a unit vector, then :math:`\mathbf{a}  \cdot \mathbf{a} = 1`, and this would be just :math:`t = \mathbf{b}  \cdot \mathbf{a}`.  

Knowing :math:`t` we can compute :math:`\mathbf{p} = t \mathbf{a}` and using :math:`\mathbf{p}` compute also :math:`\mathbf{e} =  \mathbf{b} - \mathbf{p}`.

Now, to come at this from another direction, recall the definition of the dot product

.. math::

    \mathbf{a} \cdot \mathbf{b} = a b \cos \theta

For simplicity, taking the case where :math:`\mathbf{a}` is a unit vector, we see that 

.. math::

    \mathbf{a} \cdot \mathbf{b} = a b \cos \theta = \ b \cos \theta

But above we had that

.. math::

    \mathbf{a} \cdot \mathbf{b} = t

so

.. math::

    t = \ b \cos \theta

and since

.. math::

    p =  |\mathbf{p}| = |t \mathbf{a}| = t |\mathbf{a}| = t

It follows that

.. math::

    p = \ b \cos \theta

    \frac{p}{b} = \cos \theta

And referring back to the drawing

.. image:: /figs/dot3.png
   :scale: 50 % 

*of course*

.. math::

    \cos \theta = \frac{p}{b}

In the same vein, 

.. math::

    \sin \theta = \frac{e}{b}

So if our only concern is for the magnitude of :math:`\mathbf{e}` and not its direction (suppose we are asked for the distance between the point at the end of :math:`\mathbf{b}` and the line defined using :math:`\mathbf{a}`), we should recall that

.. math::

    |\mathbf{a} \times \mathbf{b}| = a \ b \sin \theta = a \ b \ \frac{e}{b} = a e

    e = \frac{|\mathbf{a} \times \mathbf{b}|}{a}

The cross-product provides a way of computing the magnitude of :math:`e` without going through :math:`\mathbf{p}`

As a final note, it may be useful to recall that

.. math::

    (\mathbf{a} \cdot \mathbf{b} )^2 = a^2 b^2 \cos^2 \theta

    (|\mathbf{a} \times \mathbf{b}| )^2 = a^2 b^2 \sin^2 \theta

so

.. math::

    (\mathbf{a} \cdot \mathbf{b} )^2 + (\mathbf{a} \times \mathbf{b} )^2 = a^2 b^2 \cos^2 \theta + a^2 b^2 \sin^2 \theta

    = a^2 b^2

We tie it all together by going back to the diagram again

.. image:: /figs/dot3.png
   :scale: 50 % 

.. math::

    ae = \mathbf{a} \times \mathbf{b}

    e^2 = \frac{(\mathbf{a} \times \mathbf{b})^2}{a^2}
    
    p^2 = b^2 \cos^2 \theta = b^2 \frac{(\mathbf{a} \cdot \mathbf{b})^2}{a^2 b^2}  =  \frac{(\mathbf{a} \cdot \mathbf{b})^2}{a^2}
    
So

.. math::

    e^2 + p^2 =  \frac{|(\mathbf{a} \times \mathbf{b})|^2}{a^2} + \frac{(\mathbf{a} \cdot \mathbf{b})^2}{a^2}

    = \frac{1}{a^2} \ [ \  (\mathbf{a} \cdot \mathbf{b} )^2 + (|\mathbf{a} \times \mathbf{b}| )^2 \ ] 
    
    =  \frac{1}{a^2} \ (a^2 b^2)

    = b^2

But Pythagoras already told us that.

