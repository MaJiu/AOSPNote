## WindowSurfaceController

```Java
// 负责创建 SurfaceControl
```



## WindowState



## SurfaceControl

```Java
// 创建
// 1. new SurfaceSession();
// 2. new Builder(SurfaceSession);
// 3. SurfaceControl = Builder.build();
```

## Surface

```Java
// 创建
// 由 SurfaceControl 创建
// 由 SurfaceTexture 创建
public class Surface implements Parcelable {
    // Create a Surface associated with a given SurfaceControl.
    public Surface(@NonNull SurfaceControl from);
    
    // reate Surface from a SurfaceTexture.
    public Surface(SurfaceTexture surfaceTexture);
    
}
```

