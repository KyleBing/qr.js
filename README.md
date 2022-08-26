# QR.js JS 生成 PNG二维码图片

## 一、使用说明

### 1. Browser 模式
html 中引入 `qr.js`

```html
<script src="qr.js"></script>
```

生成 png 图片
```js
let linkAddress = 'https://kylebing.cn'
let qrCodeData = QRCode.generatePNG(linkAddress)
document.querySelector('.qr-code').setAttribute('src', qrCodeData)
```

### 2. Vue 模式
Vue
```html
<img :src="shareQrCode" alt="qr">
```

```js
let linkAddress = 'https://kylebing.cn'
this.shareQrCode = QRCode.generatePNG(linkAddress)
```
## 二、 option 说明


| 参数       | 可选 | 参数类型     | 可能的值                               | 说明                    |
|----------|----|----------|------------------------------------|-----------------------|
|  `version` | 可选 | `Number` | `-1`, `1` ~ `40`                   | 版本，当为 `-1` 时，使用可能的最小值 |
|  `mode` | 可选 | `String` | `numeric`, `alphanumeric`, `octet` | 默认使用最小的值              |
|  `ecclevel` | 可选 | `String` | `L` `M` `Q` `H`                    | 默认值 `L`               |

当 `generateHTML` `generatePNG` 时

| 参数       | 可选 | 参数类型     | 可能的值   | 说明                |
|----------|----|----------|--------|-------------------|
|  `modulesize` | 可选 | `Number` | `Number` | 每个方块的大小，默认为 `5`px |
|  `margin` | 可选 | `Number` | `Number` | 边框距离，默认为 `4`px    |



原文说明

```js
// the public interface is trivial; the options available are as follows:
//
// - version: an integer in [1,40]. when omitted (or -1) the smallest possible
//   version is chosen.
// - mode: one of 'numeric', 'alphanumeric', 'octet'. when omitted the smallest
//   possible mode is chosen.
// - ecclevel: one of 'L', 'M', 'Q', 'H'. defaults to 'L'.
// - mask: an integer in [0,7]. when omitted (or -1) the best mask is chosen.
//
// for generate{HTML,PNG}:
//
// - modulesize: a number. this is a size of each modules in pixels, and
//   defaults to 5px.
// - margin: a number. this is a size of margin in *modules*, and defaults to
//   4 (white modules). the specficiation mandates the margin no less than 4
//   modules, so it is better not to alter this value unless you know what
//   you're doing.

```



---

> 以下是原仓库 Readme：
# qr.js: QR code generator in pure Javascript (2011)

This is a fairly standalone script for producing QR code on the fly.
Originally developed for my own interest, the code is fully commented and well-structured.
The code is in the public domain (or to be exact, [Creative Commons Zero](https://creativecommons.org/publicdomain/zero/1.0/)),
and you can use it for absolutely any purpose.

See also a [node.js module based on qr.js](https://github.com/shesek/qruri), packaged by Nadav Ivgi.
