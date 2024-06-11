From what I could find online, `Voxels` are, essentially, the 3D equivalent of pixels. Here's an example of a `voxel` structure:
```cs
public struct Voxel {
	public Vector3 position;
	public Color color;
	public bool isActive;
	public Voxel(Vector3 position, Color color, bool isActive = true) {
		this.position = position;  
	    this.color = color;  
	    this.isActive = isActive;
	}
}
```

A voxel won't do much on its own, so we typically place these in groups called `Chunks`. Each chunk would have a specific size (i.e. number of voxels it contains). Here's an example of what that would look like in code:
```cs
public class Chunk : MonoBehaviour {  
    private Voxel[,,] voxels;  
    private int chunkSize = 16;  
  
    void Start() {  
        voxels = new Voxel[chunkSize, chunkSize, chunkSize];  
        InitializeVoxels();  
    }  
  
    private void InitializeVoxels() {  
        for (int x = 0; x < chunkSize; x++) {  
            for (int y = 0; y < chunkSize; y++) {  
                for (int z = 0; z < chunkSize; z++) {  
                    voxels[x, y, z] = new Voxel(transform.position + new Vector3(x, y, z), Color.white);  
                }  
            }  
        }  
    }  
}
```

You might've noticed that the `InitializeVoxels` method is a bit inefficient. (It is $O(n^3)$ time complex). Well, there's a shitty but clever way of getting rid of that stuff

```cs
using UnityEngine;

public class Chunk : MonoBehaviour
{
    private Voxel[] voxels;
    private int chunkSize = 16;

    void Start()
    {
        voxels = new Voxel[chunkSize * chunkSize * chunkSize];
        InitializeVoxels();
    }

    private void InitializeVoxels()
    {
        int totalVoxels = chunkSize * chunkSize * chunkSize;
        for (int i = 0; i < totalVoxels; i++)
        {
            int x = i / (chunkSize * chunkSize);
            int y = (i / chunkSize) % chunkSize;
            int z = i % chunkSize;
            Vector3 position = transform.position + new Vector3(x, y, z);
            voxels[i] = new Voxel(position, Color.white);
        }
    }
}
```

##### Explanation:
**Single Loop Initialization**:
   - We calculate the 3D coordinates (`x`, `y`, `z`) from a single loop index `i`.
   - This reduces the three nested loops into a single loop.
   - The coordinates are derived by dividing and taking the modulus of `i` with respect to `chunkSize`.

> [!error] Warning
> I'm not so sure as to how effective this is in practice. Will need to test it out separately later.



--- 

##### References
- https://procworld.blogspot.com/2013/09/voxel-instancing.html
- https://voxel.wiki/wiki/chunking/
- https://medium.com/@claygarrett/voxel-performance-instancing-vs-chunking-9643d776c11d
- https://nickmcd.me/2021/04/04/high-performance-voxel-engine/
- https://medium.com/@adamy1558/building-a-high-performance-voxel-engine-in-unity-a-step-by-step-guide-part-2-mesh-generation-bcf1401a5b4b
- https://youtube.com/playlist?list=PLcRSafycjWFdYej0h_9sMD6rEUCpa7hDH&feature=shared