.. _kepler7:

######
Hartig
######

This is a derivation of Kepler's laws from a class handout I found on the web for Math 304 by Hartig.

\section{}

We start by defining :math:`M` as the mass of the sun and :math:`m` as the mass of the planet and :math:`\mathbf{r}` as the position vector from the sun to the planet.  Combining Newton's second law and the inverse square law of gravitation we have that

.. math::

    \mathbf{F} = m \mathbf{a} = -\frac{GMm}{r^2} \ \frac{\mathbf{r}}{r}  

    \mathbf{a} = -\frac{GM}{r^2} \ \frac{\mathbf{r}}{r}  

We take :math:`\mathbf{u_r}` as a unit vector in the same direction as :math:`\mathbf{r}`.  I write :math:`\hat{\mathbf{u_r}}` without its hat ( :math:`\hat{}` ) as :math:`\mathbf{u_r}` so as not to confuse it with the derivative :math:`\dot{\mathbf{u}}_\mathbf{r}`.

.. math::

    \mathbf{r} = r \mathbf{u_r} 

    \mathbf{a} = -\frac{GM}{r^2} \ \mathbf{u_r}  

The acceleration is along the line of the radial vector, pointing toward the sun.

\section{}

The velocity is the time-derivative of the position vector :math:`\mathbf{r}`.

.. math::

    \mathbf{v} = \frac{d\mathbf{r}}{dt} = \dot{\mathbf{r}} 

and the acceleration is

.. math::

    \mathbf{a} = \frac{d\mathbf{v}}{dt} = \ddot{\mathbf{r}} 

\section{Feynman's dots, again}

We set up the angular momentum as

.. math::

    \mathbf{L} = \mathbf{r} \times \mathbf{p}  =  \mathbf{r} \times m\mathbf{v}

For a unit mass this is

.. math::

    \mathbf{r} \times \mathbf{v} =  \mathbf{r} \times \dot{\mathbf{r}} 

We compute the time-derivative

.. math::

    \frac{d}{dt} (\mathbf{r} \times \dot{\mathbf{r}}) 

by the standard vector application of the product rule which we've looked at above, this is equal to

.. math::

    =  \dot{\mathbf{r}} \times \dot{\mathbf{r}} + \mathbf{r} \times \ddot{\mathbf{r}} 

and this is equal to zero, since any vector's cross product with itself is zero, including a reversed version of itself, as in the second term.  We define a constant vector :math:`\mathbf{h}` such that

.. math::

    \mathbf{h} = \mathbf{r} \times \dot{\mathbf{r}} 

Since :math:`\mathbf{h}` is a constant, unchanging in both direction and magnitude, it defines a normal vector to the plane containing :math:`\mathbf{r}` and :math:`\dot{\mathbf{r}}`.  Align :math:`\mathbf{h}` with the :math:`z`-axis so all the motion occurs in the :math:`xy`-plane.

Note that

.. math::

    h = |\mathbf{h}| = | \mathbf{r} \times \dot{\mathbf{r}} | = rv \sin \theta 

where these are all scalar quantities and :math:`\theta` is the angle between :math:`\mathbf{r}` and :math:`\dot{\mathbf{r}} = \mathbf{v}`.

\section{Equal area}

We consider the triangle formed by the position vector before and after a short period of time :math:`\Delta t`, and the vector :math:`\Delta \mathbf{r}` connecting these two positions, where

.. math::

    \Delta \mathbf{r} \approx \dot{\mathbf{r}} \Delta t 

The little bit of area :math:`\Delta A` that is swept out during this time is

.. math::

    \Delta A \approx \frac{1}{2} \ |\mathbf{r} \times  \dot{\mathbf{r}} \Delta t | 

    \Delta A = \frac{h}{2} \ \Delta t 

So we have that

.. math::

    \frac{\Delta A}{\Delta t} \approx \frac{h}{2}  

and in the limit as :math:`\Delta t \rightarrow 0`

.. math::

    \frac{dA}{dt} = \frac{h}{2}  

(Note a difference with Feynman.  He uses :math:`A` for the area, but never actually computes its value :math:`|\mathbf{r} \times \dot{\mathbf{r}}|`.  Here, :math:`dA/dt` is the area and it's the second derivative :math:`d^2A/dt^2` that is equal to zero.  Which is another way of saying that :math:`\mathbf{h}` is constant).

\section{Manipulating :math:`\mathbf{a} \times \mathbf{h}`}

The crucial step is to prove that

.. math::

    \mathbf{a} \times \mathbf{h} = GM \dot{\mathbf{u}}_\mathbf{r} 

This takes a bit of work, so I'd like to defer it until the end.  We'll just assume it for now.  Take the equality and integrate with respect to time, obtaining

.. math::

    \int \mathbf{a} \times \mathbf{h} = \int GM \dot{\mathbf{u}}_\mathbf{r} 

    \dot{\mathbf{r}} \times \mathbf{h} = GM \mathbf{u_r} + \mathbf{d} 

where :math:`\mathbf{d}` is a constant \emph{vector} of integration.

\section{Dot product}

We're almost there now.  Take the left-hand side from above and form the dot product

.. math::

    \mathbf{r} \cdot (\dot{\mathbf{r}} \times \mathbf{h}) 

Use another vector identity to switch it around

.. math::

    = (\mathbf{r} \times \dot{\mathbf{r}}) \cdot \mathbf{h} 

But :math:`\mathbf{r} \times \dot{\mathbf{r}} = \mathbf{h}` so

.. math::

    = \mathbf{h}  \cdot \mathbf{h} = h^2 

\section{conic sections}

What we've shown is that

.. math::

    h^2 = \mathbf{r} \cdot (GM \mathbf{u_r} + \mathbf{d} ) 

    = r(GM + d \cos \theta) 

    = rGM(1 + \frac{d}{GM} \cos \theta ) 

Define :math:`k = h^2/GM` and :math:`e = d/GM`.  Then

.. math::

    k = r(1 +e\cos \theta) 

This is the equation of a conic section.  In particular, if :math:` e < 1`, then

.. math::

    r = \frac{k}{1 +e\cos \theta} 

is the equation of an ellipse.  Here is an example with :math:`k=1` and :math:`e=0.6`

.. image:: /figs/ellipse_param.png
   :scale: 50 %

\section{Cleaning up}

Here is a sketch of the situation

.. image:: /figs/Newton_vecs.png
   :scale: 50 %

As we've said all along, :math:`\mathbf{u_r}` is a unit vector in the :math:`\mathbf{r}` direction, so that :math:`\mathbf{r} = r \mathbf{u_r}`.  By the central force hypothesis, the acceleration :math:`\mathbf{a} = \dot{\mathbf{v}} = \ddot{\mathbf{r}}` is in the :math:`- \mathbf{u_r}` direction.  The source of all our complexity is that :math:`\mathbf{v} = \dot{\mathbf{r}}` is not perpendicular to :math:`\mathbf{u_r}` but forms an angle :math:`\theta` with it.

Also, we defined

.. math::

    \mathbf{h} = \mathbf{r} \times \mathbf{v} 

and aligned :math:`\mathbf{h}` with the :math:`\hat{\mathbf{k}}` direction.  We analyzed :math:`\mathbf{r} \times \mathbf{v}` to show that :math:`\mathbf{h}` is a constant vector.

:math:`\mathbf{u_\theta}` is the unit vector orthogonal to :math:`\mathbf{u_r}`.

According to Hartig, what we have to prove is that

.. math::

    \mathbf{a} \times \mathbf{h} = GM \dot{\mathbf{u}}_\mathbf{r} 

Go back to basic definitions.

.. math::

    \mathbf{r} = r \mathbf{u_r} 

    \mathbf{v} = \dot{r} \mathbf{u_r} + r \dot{\mathbf{u}}_\mathbf{r} 

Recall that :math:`\dot{\mathbf{u}}_\mathbf{r} = \dot{\theta} \mathbf{u_\theta}` so

.. math::

    \mathbf{v} = \dot{r} \mathbf{u_r} + r \dot{\theta} \mathbf{u_\theta} 

    \mathbf{h} = \mathbf{r} \times \mathbf{v} = r \mathbf{u_r} \times (\dot{r} \mathbf{u_r} + r \dot{\theta} \mathbf{u_\theta}) 

    = r^2 \dot{\theta} \hat{\mathbf{k}} 

The acceleration is

.. math::

    \mathbf{a} = -\frac{GM}{r^2} \mathbf{u}_\mathbf{r} 

So

.. math::

    \mathbf{a} \times \mathbf{h} = -\frac{GM}{r^2} \mathbf{u}_\mathbf{r} \times r^2 \dot{\theta} \hat{\mathbf{k}} 

    = -GM \dot{\theta} (- \mathbf{u_\theta}) 

    = GM \dot{\theta} \mathbf{u_\theta} 

Again, recall that :math:`\dot{\mathbf{u}}_\mathbf{r} = \dot{\theta} \mathbf{u_\theta}` so

.. math::

    \mathbf{a} \times \mathbf{h} = GM \dot{\mathbf{u}}_\mathbf{r} 

Now, integrate

.. math::

    \int \mathbf{a} \times \mathbf{h} = \int GM \dot{\mathbf{u}}_\mathbf{r} 

    \mathbf{v} \times \mathbf{h} = \dot{\mathbf{r}} \times \mathbf{h} =  GM \mathbf{u}_\mathbf{r} 
