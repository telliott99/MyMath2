.. _wave equation:

#############
Wave equation
#############

This short write-up contains a derivation of the wave equation.  We consider a violin string pinned down at the ends and then plucked.  Here is a short segment of the string (the notation doesn't match exactly what I'm going to use, but it's a place to start).

.. image:: /figs/wave1.png
   :scale: 50 %

Here, :math:`x` is not a variable but just a label for a position on the string.  We start to solve this problem by an approximation, saying that the tension :math:`T` (the force in the direction shown by the arrows), has the \emph{same magnitude} at both ends of the short interval shown as :math:`\Delta x` in the figure.

What differs between the two ends of the interval and provides a net force is the difference in the angle :math:`\theta` at the two positions :math:`x` and :math:`x + \Delta x`.  That force is

.. math::

    T \sin \theta_{x + \Delta x} - T\sin \theta_x 

which, by Newton's Law, is equal to :math:`ma`.  For this small segment of the string

.. math::

    T \sin \theta_{x + \Delta x} - T\sin \theta_x = dm \ a 

where :math:`dm` is the mass of this small segment.  You might be tempted to write :math:`\ddot{x}` (:math:`d^2 x/dt^2`) for :math:`a` here, but as we said, in this problem :math:`x` is just a label for a position on the string.

The value which changes is the displacement, which we will call :math:`\psi`.  Furthermore, if you think about it, it is clear that the displacement :math:`\psi` is a function of both time and the horizontal coordinate :math:`x`, so we need the partial derivative

.. math::

    T \sin \theta_{x + \Delta x} - T\sin \theta_x = dm \ \frac{\partial^2 \psi}{\partial t^2} 

Now, :math:`dm` is the mass of this small segment, which is equal to the mass per unit length times :math:`dx`.

.. math::

    T \sin \theta_{x + \Delta x} - T\sin \theta_x = \mu \ dx \ \frac{\partial^2 \psi}{\partial t^2} 

On the left hand side we are going to apply the small angle approximation.  Recall that

.. math::

    \sin \theta \approx \theta 

(where the next term in the series for :math:`\sin \theta` is :math:`-\theta^3/3!`).  Since :math:`\cos \theta \approx 1` then

.. math::

    \theta \approx \sin \theta \approx \tan \theta 

If you look back at the figure you will see that according to the labels there

.. math::

    \frac{\Delta u}{\Delta x} = \tan \theta 

Now, :math:`u` is what we are calling :math:`\psi` and in the limit as  this is really a partial derivative

.. math::

    \frac{\partial \psi}{\partial x} = \tan \theta \approx \sin \theta 

    T ( \frac{\partial \psi}{\partial x} \bigg |_{x + dx} - \frac{\partial \psi}{\partial x} \bigg |_{x})  =  \mu \ dx \ \frac{\partial^2 \psi}{\partial t^2} 

Now, divide both sides by :math:`T` and by :math:`dx` and let :math:`dx \rightarrow 0` and we get

.. math::

    \frac{\partial^2 \psi}{\partial x^2} =  \frac{\mu}{T}  \ \frac{\partial^2 \psi}{\partial t^2} 

This is the wave equation, but we will re-write it as

.. math::

    \frac{\partial^2 \psi}{\partial x^2} =  \frac{1}{v^2}  \ \frac{\partial^2 \psi}{\partial t^2} 

    v = \sqrt{T/\mu} 

It will turn out that :math:`v` is the velocity of the wave.

We just guess the solution

.. math::

    \psi(x,t) = A \cos kx + \omega t 

where :math:`k` is called the *wave number*.

.. math::

    \frac{\partial^2}{\partial x^2} \ \psi(x,t) = -k^2  \ \psi(x,t) 

    \frac{\partial^2}{\partial t^2} \ \psi(x,t) = -\omega^2  \ \psi(x,t) 

So

.. math::

    -k^2 = -\frac{ \omega^2}{v^2} 

    k = \pm \frac{\omega}{v} 

    \pm kv = \omega 

    \psi(x,t) = A \cos kx - \omega t 

At time zero, this function has a maximum at :math:`x=0`.  Wait a time :math:`dt`, then the maximum is when :math:`k\ dx-\omega\ dt = 0`.

.. math::

    \frac{dx}{dt} = \frac{\omega}{k} 

Substituting :math:`\omega = \pm kv`

.. math::

    \frac{dx}{dt} = \pm v 

and

.. math::

    \psi(x,t) = A \cos kx \pm kvt = A \cos k(x \pm vt) 

Clearly, the crest of the wave is moving at the velocity :math:`v`.

.. math::

    \psi(x,t) = A \cos k(x - vt) 

describes a wave moving to the right, and the opposite choice of sign means a wave moving to the left.

Note that \emph{any} function :math:`f(x - vt)` satisfies the wave equation, even

.. math::

    A e^{-k^2(x-vt)^2} 

If :math:`kx = 2 \pi` the wave repeats and by definition

.. math::

    k \lambda = 2 \pi 

    k = \frac{2 \pi}{\lambda} 

    v = \frac{\omega}{k} = \frac{\omega \lambda}{2 \pi} 

since :math:`\omega = 2 \pi f`

.. math::

    v = f \lambda 

The wavelength times the frequency is equal to the velocity.
