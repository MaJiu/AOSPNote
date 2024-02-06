```Java
/**
 * Defines common functionality for classes that can hold windows directly or through their
 * children in a hierarchy form.
 * The test class is {@link WindowContainerTests} which must be kept up-to-date and ran anytime
 * changes are made to this class.
 */
class WindowContainer<E extends WindowContainer> extends ConfigurationContainer<E>
        implements Comparable<WindowContainer>, Animatable, SurfaceFreezer.Freezable {

    // WindowContainer<Foo> 的 children 都是 Foo 类型
    // List of children for this window container. List is in z-order as the children appear on
    // screen with the top-most window container at the tail of the list.
    protected final WindowList<E> mChildren = new WindowList<E>();
}

/** Root {@link WindowContainer} for the device. */
class RootWindowContainer extends WindowContainer<DisplayContent>
        implements DisplayManager.DisplayListener {
}

/**
 * Container for grouping WindowContainer below DisplayContent.
 *
 * DisplayAreas are managed by a {@link DisplayAreaPolicy}, and can override configurations and
 * can be leashed.
 *
 * DisplayAreas can contain nested DisplayAreas.
 *
 * DisplayAreas come in three flavors, to ensure that windows have the right Z-Order:
 * - BELOW_TASKS: Can only contain BELOW_TASK DisplayAreas and WindowTokens that go below tasks.
 * - ABOVE_TASKS: Can only contain ABOVE_TASK DisplayAreas and WindowTokens that go above tasks.
 * - ANY: Can contain any kind of DisplayArea, and any kind of WindowToken or the Task container.
 *
 * @param <T> type of the children of the DisplayArea.
 */
public class DisplayArea<T extends WindowContainer> extends WindowContainer<T> {
}
```



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

