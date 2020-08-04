### ArrayBuffer
对象用来表示通用的、固定长度的原始二进制数据缓冲区你不能直接操作 ArrayBuffer 的内容，而是要通过类型数组对象或 DataView 对象来操作，它们会将缓冲区中的数据表示为特定的格式，并通过这些格式来读写缓冲区的内容。
### DataView
基于ArrayBuffer格式化地存取
- getInt8
- setInt8
### TypedArray
描述了一个底层的二进制数据缓冲区（binary data buffer）的一个类数组视图（view）
- Int8Array
- Uint8Array
- Uint8ClampedArray
- Int16Array