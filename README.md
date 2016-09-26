### openMd

1. markdown [thinker-md](https://git.oschina.net/benhail/thinker-md)
2. 桌面应用 [NW.js](https://github.com/nwjs/nw.js)

3. 如何打包

- 安装nw-builder

```
npm install nw-builder --save
```

- 新建build.js文件

```
var NwBuilder = require('nw-builder');

var nw = new NwBuilder({
  files: './package.json', // 包含文件
  platforms: ['osx64'], // 打包的平台
  version: '0.17.4', // 使用 NW.js 的版本
  macIcns: 'icon.png'
});

nw.on('log', console.log); // 日志打印函数

// 开始构建
nw.build().then(function(){
  console.log('done!');
}).catch(function(err){
  console.log(err);
});
```

- 运行命令打包，需要一点时间下载

```
node build.js
```
