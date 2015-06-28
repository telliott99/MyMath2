.. _action:

######
Action
######

In the second volume of his *Lectures on Physics*, Feynman has a great discussion of the principle he calls "least" or "stationary" action.  I want to follow his argument here.

.. image:: /figs/feynman_action1.png
   :scale: 50 %

The basic principle is that the path followed by an object is such that it minimizes the difference between the kinetic and potential energy.  This turns out to be equivalent to Newton's Laws.

In mathematical language, the principle is that this integral

.. math::

    \text{Action} = S = \int_{t_1}^{t_2} \ [ \ \frac{1}{2} m (\frac{dx}{dt})^2 - mgx \ ] \ dt 

well, he says it's not a "minimum" but it is a critical point, where the linear approximation of how it changes for a little change in the path is zero.  There are only second order terms in the correction if we shift the path a little bit.

This reminds us of an ordinary minimization problem, but it is much more complicated.  The area uses what is called the calculus of variations.  Another example of a problem in this area is to find which curve of a given length encloses the most area.  You know that the answer is a circle, but you will need the calculus of variations to prove it.

Here is what we are going to do.  We will label the path with the least action as :math:`\underline{x}`.  We will make a small perturbation to :math:`\underline{x}` such that

.. math::

    x(t) = \underline{x}(t) + \eta(t) 

    \frac{dx}{dt} = \frac{d\underline{x}}{dt} + \frac{d\eta}{dt} 

.. image:: /figs/feynman_action2.png
   :scale: 50 %

We write

.. math::

    S = \int_{t_1}^{t_2} \ [ \ \frac{m}{2} (\frac{d\underline{x}}{dt} + \frac{d\eta}{dt})^2 - V(\underline{x} + \eta) \ ] \ dt 

    (\frac{d\underline{x}}{dt} + \frac{d\eta}{dt})^2 = (\frac{d\underline{x}}{dt})^2 + 2 \frac{d\underline{x}}{dt}  \frac{d\eta}{dt} + ( \frac{d\eta}{dt})^2  

We will put any term involving :math:`\eta^2` into "a little box called 'second and higher order'" and not worry about it.

So the kinetic energy is

.. math::

    \frac{m}{2} (\frac{d\underline{x}}{dt})^2 + m \frac{d\underline{x}}{dt}  \frac{d\eta}{dt} 

We also have the potential energy

.. math::

    V(\underline{x} + \eta) 

We write a standard Taylor Series expansion (:math:`\eta` is small)

.. math::

    V(\underline{x} + \eta) = V(x) + \eta V'(\underline{x}) + \frac{\eta^2}{2} V''(\underline{x}) + \dots 

again neglecting second-order terms we have then

.. math::

    V(\underline{x} + \eta) = V(x) + \eta V'(\underline{x}) 

so

.. math::

    S =  \int_{t_1}^{t_2} \ [ \  \frac{m}{2} (\frac{d\underline{x}}{dt})^2 + m \frac{d\underline{x}}{dt}  \frac{d\eta}{dt} - V(x) + \eta V'(\underline{x})  \ ] \ dt 

We want to concentrate on the difference between this :math:`S` and :math:`\underline{S}`, the path of least action.  Let's call that difference :math:`\delta S`

.. math::

    \delta S =  \int_{t_1}^{t_2} \ [ \  m \frac{d\underline{x}}{dt}  \frac{d\eta}{dt} -  \eta V'(\underline{x})  \ ] \ dt 

Now, we are going to use integration by parts to make the derivative of :math:`\eta` disappear.

.. math::

    \frac{d}{dt} (\eta f) = \eta \frac{df}{dt} + f \frac{d\eta}{dt} 

    f \frac{d\eta}{dt} =  \frac{d}{dt} (\eta f) - \eta \frac{df}{dt} 

    \int f \frac{d\eta}{dt} =  \int \frac{d}{dt} (\eta f) - \int \eta \frac{df}{dt} 

    \int f \frac{d\eta}{dt} =  \eta f - \int \eta \frac{df}{dt} 

    \int f \frac{d\eta}{dt} \ dt =  \eta f - \int \eta \frac{df}{dt} \ dt 

In our problem

.. math::

    f = m \frac{d \underline{x}}{dt} 

We had

.. math::

    \delta S =  \int_{t_1}^{t_2} \ [ \  m \frac{d\underline{x}}{dt}  \frac{d\eta}{dt} -  \eta V'(\underline{x})  \ ] \ dt 

and now we have

.. math::

    \delta S =  m \frac{d \underline{x}}{dt} \eta(t) \bigg |_{t_1}^{t_2} - \int_{t_1}^{t_2}  \frac{d}{dt} (\  m \frac{d\underline{x}}{dt}) \ \eta(t) \ dt  -  \int_{t_1}^{t_2}  V'(\underline{x})   \eta(t) \ dt 

Feynman says:  

    Now comes something which always happens---the integrated part disappears."  The reason is that we must start and finish all the paths at the same place.  This means that :math:`\eta` is zero at both :math:`t_1` and :math:`t_2`, and so the first term goes away.  We factor out the :math:`\eta(t)` in the rest of it to obtain

.. math::

    \delta S =   \int_{t_1}^{t_2} \ [ \ -\frac{d}{dt} (\  m \frac{d\underline{x}}{dt}) - V'(\underline{x}) \ ] \  \eta(t) \ dt 

    \delta S =   \int_{t_1}^{t_2} \ [ \ - m \frac{d^2\underline{x}}{dt^2} - V'(\underline{x}) \ ] \  \eta(t) \ dt 

Our principle of least action says that :math:`\delta S = 0` for \emph{any} :math:`\eta`.  So that means that what multiplies :math:`\eta` must be equal to zero.

.. math::

    - m \frac{d^2\underline{x}}{dt^2} - V'(\underline{x})  

    - V'(\underline{x})  = m \frac{d^2\underline{x}}{dt^2}  

    - V'(\underline{x})  = m a  

and the force is the derivative of the potential with respect to position (with a minus sign), thus

.. math::

    F  = m a  

There is a lot more in the lecture, but I will leave it at this.  Feynman closes this section by saying

    One remark: I did not prove it was a minimum - maybe it's a maximum. In fact, it doesn't really have to be a minimum. It is quite analogous to what we found for the principle of least time which we discussed in optics. There also, we said at first it was *least* time. It turned out, however, that there were situations in which it wasn't the least time. The fundamental principle was that for any first-order variation away from the optical path, the change in time was zero; it is the same story. What we really mean by least is that the first-order change in the value of S, when you change the path, is zero. It is not necessarily a minimum
