.. _Auroux 19:

#########
Auroux 19
#########

Before I start notes on the lecture, I'd like to summarize where we're going.

We imagine an object moving along a trajectory or curve :math:`C`.  It is moving in a vector field :math:`F=f(x,y)`, which varies with position.  At each point along the curve we want to compute :math:`\mathbf{F} \cdot d \mathbf{r}`, the dot product of :math:`\mathbf{F}` with the next little bit of our trajectory.  We take the part of :math:`\mathbf{F}` in the same direction as :math:`\mathbf{dr}` and then sum up all those little bits to find the total work

.. math::

    \int \mathbf{F} \cdot \mathbf{dr} = W = \int \mathbf{F} \cdot \mathbf{v} \ dt = \int \mathbf{F} \cdot \mathbf{\hat{T}} \ ds 

Now, :math:`\mathbf{F} \cdot \mathbf{dr}` looks a little overwhelming.  How do you integrate a couple of vectors?  Even :math:`\mathbf{F} \cdot \mathbf{v}` too, for that matter, and what is :math:`\mathbf{\hat{T}}`?  However, if we break this up into components, it should make more sense.

The way to understand :math:`\mathbf{\hat{T}}` is

.. math::

    \mathbf{dr} = ds \ \mathbf{\hat{T}} 

What this means is that the vector :math:`\mathbf{dr}` is in the direction :math:`\mathbf{\hat{T}}`, the unit vector tangent to the curve, and it has magnitude :math:`ds`, the little bit of arc length.  One way to see this is to divide by :math:`dt`

So

.. math::

    \frac{\mathbf{dr}}{dt} = \mathbf{v} 
    
    = \frac{\mathbf{dr}}{ds}  \ \frac{ds}{dt} =  \frac{ds}{dt} \ \mathbf{\hat{T}} 
    
    =  \left| v \right|\ \mathbf{\hat{T}} 

So what we are doing here is, at each point along the curve there is the next little change in the :math:`\mathbf{r}` vector, :math:`\Delta \mathbf{r}` and we want

.. math::

    \lim_{\Delta \mathbf{r} \to 0} \sum_i \mathbf{F} \cdot \Delta \mathbf{r} 
    
    =  \lim_{\Delta t \to 0} \sum_i \mathbf{F} \cdot \frac{\Delta \mathbf{r}}{\Delta t} \Delta t
    
    = \int_C \mathbf{F} \cdot \mathbf{dr} 
    
    = \int_{t=t_0}^{t=t_1}  \mathbf{F} \cdot \frac{\mathbf{dr}}{dt} dt 

Notice the change in limits that goes with the switch to :math:`dt`.

Now, in the end we will actually compute using a formula like this

.. math::

    \int_C \mathbf{F} \cdot \mathbf{dr} = \int \langle M \ \mathbf{\hat{i}},N\ \mathbf{\hat{j}} \rangle \ \cdot \langle dx,dy \rangle  

with one important reservation.  We need to simplify this integral to have a single variable.  We can't really integrate :math:`\int .. \ dx \ dy`.  We can only do this because :math:`x` and :math:`y` are related by their trajectory.  We may use a parameter :math:`t`, or perhaps, just express :math:`y` in terms of :math:`x`.

.. math::

    \int_C \mathbf{F} \cdot \frac{\mathbf{dr}}{dt} \ dt = \int \langle M,N \rangle \ \cdot \langle \frac{dx}{dt}, \frac{dy}{dt} \rangle dt 

But we have to express things in terms of a single variable.  Then we will have a simple integral over a single variable.

Before we do that, let's review a couple of vector fields.

Field 1.  :math:`F = \langle \mathbf{\hat{i}}, \mathbf{\hat{j}} \rangle`  This field is the same everywhere :math:`\langle 1,1 \rangle`.

Field 2.  :math:`F = \langle x \mathbf{\hat{i}}, 0 \rangle`  This field is proportional to :math:`x`, points left and right (:math:`\Delta y = 0`), and reverses sign at the y-axis.

Field 3.  :math:`F = \langle x \mathbf{\hat{i}},y \mathbf{\hat{j}} \rangle`  This is a radial field, with magnitude proportional to :math:`r`.

Field 4.  :math:`F = \langle -y \mathbf{\hat{i}},x \mathbf{\hat{j}} \rangle`  This is a rotating field.  At :math:`\langle 1,1 \rangle` the field is :math:`\langle -1,1 \rangle` and at every point the field is :math:`\perp r`.  The magnitude is proportional to :math:`r`, so it's like a rotating disk.

Example 1.

.. math::

    F = -y \mathbf{\hat{i}} + x \mathbf{\hat{j}}

which is the rotating field.  :math:`\mathbf{r}(t)` is

.. math::

    x = t 

    y = t^2 

    0 \le  t \le  1 

The curve is just :math:`y=x^2`, parametrized.  We have

.. math::

    \int_{t=0}^{t=1} F \cdot \frac{dr}{dt} \ dt = \int_0^1  \langle -y,x \rangle  \ \cdot \ \langle \frac{dx}{dt},\frac{dy}{dt} \rangle  \ dt 

    \langle -t^2, t \rangle  \ \cdot \langle 1, 2t \rangle  \ dt 

    \int_0^1 t^2 \ dt = \frac{1}{3} 

We could have said

.. math::

    \int_C  M \ dx + N \ dy = -y \ dx + x \ dy 

and expressed :math:`y` in terms of :math:`x`.  This works out the same as before, because :math:`y=x^2`, :math:`dy = 2x \ dx` so we have

.. math::

    \int_C  M \ dx + N \ dy 
    
    = \int -x^2 \ dx + x \ 2x \ dx 
    
    = \frac{x^3}{3} = \frac{1}{3}

with limits :math:`x=0` and :math:`x=1` (because we had :math:`t=0` and :math:`t=1` and :math:`x=t`).

Example 2.  The curve :math:`C` is a circle of radius :math:`a` centered at the origin, going ccw, and the field is :math:`F = \langle x \mathbf{\hat{i}},y \mathbf{\hat{j}} \rangle`.  Now you could set this up and solve it, but you can also notice that we are doing

.. math::

    \int \mathbf{F} \cdot \mathbf{\hat{T}} \ ds 

and at every point on the curve the radial vector for the field :math:`\langle x,y \rangle  \perp \mathbf{\hat{T}}`, so the whole thing is is just 0.

Example 3.  The curve :math:`C` is again a circle of radius :math:`a` centered at the origin, going ccw, and the field is the rotating one, :math:`F = \langle -y,x \rangle`.  Now you can notice that

.. math::

    \mathbf{F} \cdot \mathbf{\hat{T}} =  |F| = \sqrt{x^2 + y^2} = a 

so we have

.. math::

    \int_C \mathbf{F} \cdot \mathbf{\hat{T}} \ ds =  \int_C a \ ds = 2 \pi a^2 

if you fail to see this, then you can say we have

.. math::

    \int_C M \ dx + N \ dy = \int_C -y \ dx + y \ dy 

and

.. math::

    x = a \cos \theta, \ \ dx = -a \sin \theta \ d \theta 

    y = a \sin \theta, \ \ dy = a \cos \theta \ d \theta 

The first term becomes :math:`a^2 \sin^2 \theta \ d \theta` and the second is :math:`a^2 \cos^2 \theta \ d \theta` and so

.. math::

    \int_C a^2 d \theta = 2 \pi a^2 
