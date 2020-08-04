### Blob
本质： ArrayBuffer + Type + length
- arraryBuffer() 获取Arraybuffer
- stream()
- text() 把ArrayBuffer utf-8编码
- slice() 切割ArrayBuffer生成新的Blob
### FileReader
- abort()
- readAsArrayBuffer()
- readAsBinaryString()
- readAsDataURL()-创建base64
- readAsText()
### URL(创建引用)
- URL.createObjectURL
- URL.revokeObjectURL
### createImageBitMap
- createImageBitmap