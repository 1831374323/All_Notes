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

