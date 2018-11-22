



<h1 align="center">
miniprogram-qrcode-image
</h1>

支持将小程序码合成到指定模板图片上


## 安装

```
npm install miniprogram-qrcode-image --save
```
#### windows
windows依赖于`libvips`，由于安装时候下载该库较慢，请参考下面方法安装
* 进入 `npm-cache` 目录，一般`npm-cache`位于 (输入 `npm root -g`) 的同级目录
* 下载 https://share.weiyun.com/5ZIyyAH 复制到 `/npm-cache/_libvips/` 下
* `npm install miniprogram-qrcode-image --save`

#### linux
> 在 linux 下安装的时候会可能会报`libvips`相关的错误，因为`sharp`库依赖于`libvips`，首先安装`libvips`
```
wget https://github.com/libvips/libvips/releases/download/v8.7.1/vips-8.7.1.tar.gz
tar xf vips-8.7.1.tar.gz
cd vips-8.7.1
./configure
make
sudo make install
sudo ldconfig
```

然后

```
npm install miniprogram-qrcode-image --save
```



## 使用



```js
const path = require('path')
const miniprogramImage = require('miniprogram-qrcode-image')

let mySharp = new miniprogramImage(path.join(__dirname, '../template.png')); // 传入指定的模板图片 如下图。

```

![template.png](https://i.loli.net/2018/11/16/5bee70edc46da.png)

### renderImage

```js
let renderBuffer = await mySharp.renderImage(info.image, // 二维码图片的 buffer 数组 
{ 
  width: 200, // 重新设置二维码宽度
  left: 54, // x轴偏移
  top: 217 // y轴偏移
})

// 返回渲染好的buffer数组
```

`渲染效果`

![output.png](https://i.loli.net/2018/11/16/5bee716374ba7.png)


## LICENSE
<a href="http://opensource.org/licenses/MIT">MIT</a>

