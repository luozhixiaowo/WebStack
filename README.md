<h1 align="center"><a href="https://github.com/luozhixiaowo/WebStack" target="_blank">WebStack-Screenshot</a></h1>
<p align="center">网站截图 API</p>

请求方法: GET | POST

| 属性      | 默认值 | 类型          | 描述                                                                      |
| --------- | ------ | ------------- | ------------------------------------------------------------------------- |
| url       |        | String        | 请求的网站 URL 地址，如果输入的是域名会自动拼接`http://`                  |
| type      | png    | String        | 图片类型，`png`、`jpeg`、`webp`                                           |
| cache     | 86400  | Int & Boolean | 缓存，默认缓存为 1 天，传入`false`禁用缓存，传入数字如:`123`则缓存 123 秒 |
| quality   |        | Int           | 图片质量**0-100**之间，如果是图片类型是`png`则被忽略                      |
| viewport  |        | Int           | 截图 100 宽 200 高，格式`100x200`                                         |
| fullPage  | true   | Boolean       | 截取完整页面，如果使用`clip`属性需要手动设置为`false`                     |
| isMobile  | false  | Boolean       | 是否是手机端                                                              |
| await     | 0      | Int           | 页面渲染完成后等待，`0`表示不等待(单位毫秒)                               |
| timeout   | 30000  | Int           | 截图超时，`0`表示无限制(单位毫秒)                                         |
| encoding  | binary | String        | 图片编码，`binary`、`base64`                                              |
| clip      |        | String        | 剪切指定区域，接收 4 个单位以英文**逗号**分割分别是`x,y,width,height`     |
| font      |        | String        | 如果指定的截图网站出现乱码，你可通过该参数指定字体`url`地址               |
| waitUntil | load   | String        | 在什么时机触发截图，[详细请看下方另一个表格 ](#waituntil)                 |

### waitUntil

| 属性             | 描述                               |
| ---------------- | ---------------------------------- |
| load             | 在 load 事件触发时完成             |
| domcontentloaded | 在 DOMContentLoaded 事件触发时完成 |
| networkidle0     | 500ms 内没有任何网站请求时         |
| networkidle2     | 500ms 内只有 2 个请求时            |
