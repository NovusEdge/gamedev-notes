Well, every 1st person game needs an interaction system. Based on where a player is looking, they either should trigger something or be able to do something to an object if the game allows it. 

Before doing this, we must first define the [[Control Schemes | Control Scheme]] for the game. One of the most common interaction controls on controllers is $\Delta$, and on keyboards it is either `E/F`. Assuming this is what we're following, we can define a primitive system like so:

```cs

public interface Interactable {
    void Interact(GameObject interactee);
}

public class CameraInteract: MonoBehavior {
    [SerializeField] private GameObject player;
    [SerializeField] private float interactionRange;
    [SerializeField] private LayerMask interactableLayer;

    void Awake() {
        if (player == null) {
            player = GameObject.FindWithTag("Player");
        }

        StartCoroutine(Interactor());
    }
    
    public IEnumerator Interactor() {
        Interactable interactable;
        RaycastHit hit;
        while (true) {
            if (Physics.Raycast(player.transform.position, player.transform.forward, out hit, interactionRange, interactableLayer)) {
                if (!hit.collider.TryGetComponent<Interactable> (out interactable)) { return; })
                interactable.Interact(player);
            }
            yield return null;
        }
    }
}


```

This script would go into the `Player`'s camera. Now, any object that needs to be interactable need only extend the `IInteractable` (`I` is a prefix for the interface) interface and implement the `Interact` method.
```cs
public class SomeObject: MonoBehavior, IInteractable {
	// ---- Snip ----
    public void Interact(GameObject interactee) {
        // ---- Logic and stuff to execute when interacted with ----
    }
}
```

> [!Note] Note
> Be sure to set the `Interact` bindings in the project preferences for unity since this relies on that.










