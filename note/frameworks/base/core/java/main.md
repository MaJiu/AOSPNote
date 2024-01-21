## SurfaceView

MVC 模型

```java
public class SurfaceView extends View implements ViewRootImpl.SurfaceChangedCallback {

}

public interface SurfaceHolder {
}

public class Surface implements Parcelable {
}
```

### 基本原理

既是一个普通的 view，同时还维护一个 surface，通过在 view 上挖洞露出 surface

```bash
# SurfaceView  的 Layer 结构
Creates the surface control hierarchy as follows
	ViewRootImpl surface
     bounds layer (crops all child surfaces to parent surface insets)
       * SurfaceView surface (drawn relative to ViewRootImpl surface)
           * Blast surface (if enabled)
       * Background color layer (drawn behind all SurfaceView surfaces)
```

### 生命周期

 核心处理逻辑在 updateSurface

createSurfaces  updateSurface 内调用

releaseSurfaces (释放 SurfaceControl 从 SurfaceFlinger 移除相应 Layer)调用时机

1. SurfaceView  从 所在的 window detach `onDetachedFromWindow`
2. SurfaceView 所在的 window  的 surface 已经销毁或不可用

`SurfaceHolder.surfaceDestroyed` 回调时不一定执行 releaseSurfaces，比如不可见时

### 使用方法
