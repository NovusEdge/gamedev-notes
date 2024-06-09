Assuming that the movement in the platformer follows the following (in unity) : 

```csharp fold title="Unity Horizontal Movement"
private float horizontalInput;
private float playerSpeed = 5.0f;

private Rigidbody2D PLAYER_RB;

private void Start()
{
	PLAYER_RB = GetComponent<RigidBody2D>;
}

private void Update() 
{
	horizontalInput = Input.GetAxis("Horizontal");
	PLAYER_RB.AddForce(new Vector2(horizontalInput * playerSpeed, 0), ForceMode2D.Impulse);
}
```

Pretty basic. Now, to implement _good_ jumping mechanics there's a couple of things to consider. 

# 1. `FixedUpdate`  or `Update`?
Depending on the type of platformer, it might be necessary to move to the `FixedUpdate` method. (Read up on [[FixedUpdate vs. Update]]), essentially, `FixedUpdate` should be used **when applying forces, torques, or other physics-related functions**. Perfect for _Pixel Perfect Platformers_.





---
## References
- [The Mechanics Behind Satisfying 2D Jumping](https://kotaku.com/the-mechanics-behind-satisfying-2d-jumping-1761940693)
- [Jumping controls in 2D pixel-perfect platformers](https://pavcreations.com/jumping-controls-in-2d-pixel-perfect-platformers/)
- [Guide on Jumping in platformers](https://forum.defold.com/t/guide-on-jumping-in-platformers/71882)
- 