Here's Newton's 3 laws of motion:
1. _Every body preserves in its state of rest, or of uniform in a right line, unless it is compelled to change that state by forces impressed thereon._
2. _The alteration of motion is ever proportional to the motive force impressed: and is made in the direction of the right line in which that force is impressed._
3. _To every action there is always opposed an equal reaction: or the mutual actions of two bodies upon each other are always equal, and directed to contrary parts._

## Some Important Derivations

Let us establish some fundamentals:
- **Speed** is a _scalar_ quantity that represents the _distance_ traveled by an object per unit time.
- **Velocity** is a _vector_ quantity that represents the _displacement_ of an object per unit time.

Mathematically we can represent these as: $s = \frac{\Delta D}{\Delta t}$, $v = \frac{\Delta x}{\Delta t}$. _Instantaneous velocity_ is the velocity of an object at an instance of time. This may be written as: $$v_{inst} = \lim_{\Delta t \rightarrow 0}{\frac{\Delta x}{\Delta t}} = \frac{dx}{dt}$$
- **Acceleration** is another _vector_ quantity that represents the change of velocity over time. $$a = \frac{\Delta v}{\Delta t}$$This may also be written in the form of a derivative (as we did with velocity):$$a = \lim_{\Delta t \rightarrow 0}{\frac{\Delta v}{\Delta t}} = \frac{dv}{dt} = \frac{d^2x}{dt^2}$$
--- 

We can now use this information to derive 3-4 very important equations for 2 dimensional motion. before we proceed, let us establish some notations: 
- $v$ or $v_{f}$: final velocity
- $u$ or $v_{i}$: initial velocity
- $a$: acceleration
- $t$: time
- $S/s$ or $x$: displacement/distance (interchangeable unless specified)

1. $v = u + a\Delta t$ 
To derive this equation, we must first write acceleration in it's derivative form: $$a = \frac{dv}{dt}$$Now we can rearrange this as: $$a \cdot dt = dv$$
Integrating both sides we get: $$\int_{t_{start}}^{t_{end}}{a \cdot dt} = \int_{u}^{v}{dv}$$ $$a \Delta t = (v - u)$$ Rearranging the terms we can get the final equation: $$v = u + a \Delta t$$

2. $s = u \Delta t + \frac{1}{2}a \Delta t^2$ 
To derive this equation we start with the following: $$v = \frac{ds}{dt}$$Which we can write as: $$v \cdot dt = ds$$Using the previously derived equation we can write: $$(u+at)dt = ds$$ $$udt + atdt = ds$$ Integrating both sides: $$\int_{0}^{t}{(udt + atdt)} = \int_{0}^{s}ds$$ $$s = \int_{0}^{t}{(u \cdot dt}) + \int_{0}^{t}{(at \cdot dt)} $$ $$s = ut + \frac{1}{2}at^2$$
3. $2as = v^{2}- u^{2}$
To derive this one, we start off by considering the derivative form of acceleration: $a = \frac{dv}{dt}$ and the derivative form of velocity: $v= \frac{ds}{dt}$. If we cross multiply these two, we get: $$a\frac{ds}{dt} = v\frac{dv}{dt}$$We can simplify this and integrate both sides:$$\int_{0}^{s}{a \cdot ds} = \int_{u}^{v}{vdv}$$ $$as = \frac{1}{2}(v^2-u^2)$$$$\implies 2as = v^{2}- u^2$$
## Friction
- Friction is proportional to the **normal force** between the contacting surfaces. The normal force exerted by an object is the component of the force vector normal, that is, perpendicular, to the surface that is in contact with the object.

![[Friction_StillObject.png | 500]]

![[Friction_RampNormal.png | 500]]

![[Friction_AppliedForce.png | 500 ]]

The coff. of friction is the measure of the extent of friction experienced by one body with relation to another with respect to it's physical properties and conditions. When the objects are motionless, the coefficient of static friction, $\mu_s$ , governs the frictional force. When the objects begin to slide, the friction between them usually decreases, and the frictional force is defined by the coefficient of kinetic friction, $\mu_{k}$. The coefficient of friction is a static quantity without units (since it's a ratio).

Since force is a vector quantity, the net force on a body in 3D is equal to the vector sum of all it's component forces along the 3 axes. This can be represented as: $$\vec{F_{net}} = \vec{F_{x}}+\vec{F_{y}}+\vec{F_{z}}$$ and the magnitude is given by: $$|\vec{F_{net}}| = \sqrt{|\vec{F_{x}}|^2 + |\vec{F_{y}}|^2 + |\vec{F_{z}}}|^2$$

One of the most important types of forces that you'd encounter when dealing with physics in games is the gravitational force. For 2 bodies of masses $m_{1}$ and $m_{2}$, separated by a distance of $r$, the gravitational force between them is given by: $$F_{G} = \frac{Gm_{1}m_{2}}{r^{2}}$$The value $G$ is known as the gravitational constant, which is an _empirical physical constant_. The value of $G$ is: $6.674 \cdot 10^{-11} Nm^{2}/kg^{2}$.

Considering that one of the bodies remains stationary, we can simplify the equation as: $$F_{G}= mg_{i}$$The value $g_{i}$ is the gravitational acceleration experienced by any object under the influence of the actuator. 

## Springs
A relation known as Hooke’s Law describes the force, $F_{s}$, exerted at either end of the spring.
![[Springs_Hookes_Law.png]]

According to Hooke’s Law, if a spring with a weight on the end of it is extended and released, it will oscillate forever about its equilibrium location. Of course, in reality this perpetual motion doesn’t occur and the spring motion gradually decreases until the spring comes to a rest. The gradual decrease in motion is due to a damping force that is proportional to the difference in velocity of the two ends of the spring.


## Centripetal Force

![[Centripetal_Force.png]]

***NOTE:*** *Centripetal* force is the one that produces an _inwards_ influence, and centrifugal force is one where the influence is towards the outwards direction. 

![[Centripetal_vs_Centrifugal.png | 500]]

Mathematically represented, the equation for centripetal force looks very similar to that of gravitational force: $$F_{c} = \frac{mv^2}{r}$$

#### Spring + Ramp

![[Spring_Ramp.png]]

The force component parallel to the ramp is given by:
$$F_{p} = mg\cdot (\sin{\theta} - \mu \cos{\theta}) - k \Delta x$$
## Work
Work is performed when a force, $F$, is applied to an object over a distance, $d$. $$W = F \cdot d$$
The SI unit for work done is _Joules_ ($J$)
## Energy
Energy is defined as the capacity for doing work. Energy is a state variable, meaning that it is used to characterize the physical state of an object. Energy, work, and force are closely related. 

There are several different forms that energy can take. **Kinetic energy** is related to the motion of an object. **Potential energy** can be thought of as stored energy and is related to the position of an object. If work is performed to move an object from one location to another, part or all of that work might be stored in the object as potential energy. Taken together, the kinetic and potential energies of an object are also referred to as the **mechanical energy** of the object. . The internal energy type you are probably most familiar with is **thermal energy**, which is related to the temperature of an object. Objects can also store **chemical energy**.


### Kinetic Energy
The kinetic energy of an object, $E_{K}$,is directly proportional to the mass of the object and the square of the velocity. 

$$E_{K} = \frac{1}{2}mv^2$$
Work may be represented as: $$W = \frac{1}{2}m(v_{f}^{2} - v_{0}^2)$$

Work is performed on the projectile as it travels upwards. When the projectile reaches its highest point, its velocity is zero, meaning that all of its kinetic energy has been converted to work. The height,$h$, that the projectile will reach can be found by equating its original kinetic energy to the work performed on it. $$\frac{1}{2}mv^{2}= mgh \implies h_{max} = \frac{v^2}{2g}$$
### Potential Energy
