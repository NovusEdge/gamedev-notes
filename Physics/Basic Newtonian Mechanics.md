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

