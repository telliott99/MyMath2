.. _potential:

##########
Potentials
##########

If a given field :math:`\mathbf{F}` is the gradient of a function :math:`f`, then we call the function :math:`f` the *potential*, and we can calculate

.. math::

    \int \mathbf{F} \cdot d \mathbf{r}

as simply 

.. math::

    \int \mathbf{F} \cdot d \mathbf{r} = f(P1) - f(P2)

The curl must be zero for this to work.  In fact, saying that the curl is zero and that :math:`\mathbf{F} = \nabla f` are equivalent statements.

The curl must be zero!

If :math:`\mathbf{F}` comes from a potential :math:`f` then

.. math::

    \mathbf{F} = \langle fx, fy, fz \rangle

In 2D the curl was

.. math::

    \mathbf{F} = \langle M, N \rangle

    \text{curl} \ \mathbf{F} = N_x - M_y

In space there will be three components and *all three components of the curl must be zero*:

.. math::

    \mathbf{F} = \langle P, Q, R \rangle

    Q_x = P_y
    
    R_x = P_z
    
    Q_z = R_y
    
This is the same thing as saying that the mixed second derivatives will be zero for :math:`f`

.. math::

    f_{yz} = f_{zy}

and so on!

Another way to say this is that
    
.. math::

    P_x dx + Q_y dy + R_z dz = df

it is an *exact* differential.

