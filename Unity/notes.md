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

