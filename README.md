# web打印代理
## 简介
一款静默打印代理工具，通过建立Socket服务，接收打印指令，通过解析打印指令完成打印。  
A silent print proxy tool that receives print commands by creating a Socket service and prints by parsing print instructions.
## 使用方式
1. 下载源码或者release版
2. 运行.exe文件
3. 打开测试页 `index.html`
4. 点击测试页的打印按钮
## 可视化编辑的demo
运行svg项目的index.html ,矩形框表示条码区域，双击矩形框可以编辑大小，文字和矩形框可拖动；运行代理后点击打印即可;  
Run the index.html of the svg project. The rectangle box indicates the barcode area. Double-click the rectangle to edit the size. The text and rectangle can be dragged. After running the proxy, click Print.
### 系统功能
* 最小化到状态栏
* 单实例
* 设置默认打印机
* 保留异常日志
* 保留打印日志
* 打印结果反馈

### 打印功能
* 自定义纸张大小;Custom paper size
* 打印条形码，二维码;Print barcode, QR code;
* 打印图片

## 指令示例
* JSON格式
* 类型：text/qrcoe/datamatrix/barcode/line/image
* 单位：毫米
* 文字换行手动使用`\r\n`

web->代理
```
{
  "id":1537148688,
  "page":{
      "width":210,
      "height":297
  },
  "content":
  [
    {
      "type":"text",
      "text":"改需求推荐使用支付宝",
      "size":20,
      "x":65,
      "y":100
    },
    {
      "type":"line",
      "x1":0,
      "y1":130,
      "x2":210,
      "y2":130
    },
    {
      "type":"qrcode",
      "text":"https://qr.alipay.com/tsx04136zdm6mxp7jvv4s2f",
      "width":70,
      "height":70,
      "x":70,
      "y":15
    }
  ]
}
```
代理->web
```
{
  id:1537148688,
  code:0,//0成功，1失败
  msg:"返回的消息"
}
```
