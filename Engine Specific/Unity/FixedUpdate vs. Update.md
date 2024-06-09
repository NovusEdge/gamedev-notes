> Update runs once per frame. `FixedUpdate` can run once, zero, or several times per frame, depending on how many physics frames per second are set in the time settings, and how fast/slow the frame-rate is.

It's for this reason that `FixedUpdate` should be used **when applying forces, torques, or other physics-related functions** - because you know it will be executed exactly in sync with the physics engine itself.

Whereas `Update()` can vary out of step with the physics engine, either faster or slower, depending on how much of a load the graphics are putting on the rendering engine at any given time, which - if used for physics - would give correspondingly variant physical effects!

---
##### Reference
- https://stackoverflow.com/questions/34447682/what-is-the-difference-between-update-fixedupdate-in-unity
- https://learn.unity.com/tutorial/update-and-fixedupdate