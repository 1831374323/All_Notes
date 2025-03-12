# 生命周期

https://docs.unity3d.com/2022.3/Documentation/Manual/ExecutionOrder.html

### 开始阶段

Awake()

OnEnable()

Start()

### 物理阶段

FixedUpdate()

Internal animation update and Internal physics update

OnTrigger...()

OnCollision...()

yield WaitForFixedUpdate()

### Input events

OnMouse...()

### 游戏逻辑 

Update()

yield ...

Internal animation Update

lateUpdate()

### 场景渲染

### Gizmo 渲染

### GUI 渲染

### 帧结束

yield WaiForEndOfFrame

### Pausing

### 销毁和退出

OnApplicationQuit()

OnDisable()

OnDestory()

# ECS架构

https://zhuanlan.zhihu.com/p/59879279

Entity-Component-System

![image](https://github.com/user-attachments/assets/afc08808-3ae5-401b-810b-50074f3c85ea)

Entity-Unity GameObject

Component-Unity Component

# 物理

### 刚体

rigidbodyType 会导致不同的碰撞结果

* Dynamic
* Kinematic
* Static

### 碰撞

碰撞控制的三种方式优先级如下：

Physics2D.IgnoreCollision > Layer Overrides > Layer Collision Matrix

Layer Overrides: collider的一个属性

# Layer

LayerMask: 用于表示一个或多个图层的位掩码。

NameToLayer等返回的是index,和LayerMask掩码不同。

例：NameToLayer.("六号图层") --> 6

layerMask --> 100 0000 --> 64

正确转换: layerMask = 1 << LayerMask.NameToLayer("六号图层")

# 图形

## Texture 贴图

### SDF

Signed Distance Field (有向距离场)

贴图记录的信息不是颜色，而是距离。像素上的每个点都记录了这个点到字样边缘的距离，存储在贴图的Alpha通道中。

着色器对贴图进行采样并放大时，会进行插值。对于一般贴图，即是对颜色进行插值，信息的缺失就会造成纹理的模糊失真。而对距离插值则不一样，即使贴图只提供了有限的信息，但我们可以保证插值后的结果依然正确。

可以看作一种矢量的渲染方式。只能针对图案纹样一类的图片进行处理，即边缘明晰的单色图样。

#### SDF的应用

**字体渲染：**

Unity中的TextMeshPro。

**形变动画:**

**Ray-Marching：（光线步进）**
