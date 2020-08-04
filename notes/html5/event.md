### eventTarget
- addEventListener
- removeEventLister
- dispatchEevent()
### 事件阶段
- Event.NONE:0 // 无
- Event.CAPTURING_PHASE:1 // 捕获阶段 
- Event.AT_TARGET:2 // 目标阶段 
- Event.BUBBLING_PHASE:3 // 冒泡阶段 
默认情况下在捕获阶段不触发事件，只是在冒泡阶段触发事件，如果打开事件监听的捕获模式则先触发捕获阶段再触发冒泡阶段
### event
property
- target 等同于 srcTarget --- 触发目标
- currentTarget --- 传播过程中的目标
- cancelable 是否可以取消默认行为
- defaultPrevented 是否已经组织默认行为
- cancelBubble 属性
- eventPhase 体现事件的阶段
- isTrusted 事件是否是由用户行为生成（不是通过dispathEvent触发）
- originalTarget
- type 事件类型
method
- stopPropagation 阻止事件传播，影响cancelBubble属性
- preventDefault 阻止默认行为，影响defaultPrevented属性和returnValue属性
- stopImmediatePropagation() 当一个类型注册了多个函数时调用了此方法后其他函数不再执行
### 自定义事件
- 直接new Event - 自定义所有事件
- document.createEvent 创建MessageEvent ElementEvent等内置事件
### 后代
UIEvent
MessageEvent