---
layout: post
title: "React Native快速初始化"
subtitle: “ReactNative快速初始化教程”
header-img: "img/post-bg-default1.png"
date: 2016-1-20
tags: 
 - Android
 - iOS
---


按照本操作流程可以快速初始化RN项目。

1. 科学上网
 
2. `brew install nvm`   安装nvm（homebrew自己装,update一下homebrew）

3. `nvm install node && nvm alias default node ` (注意brew装的node的default版本可能和淘宝镜像不一致，自己nvm切换)

4. `npm cache clean` 

5. `npm config set registry=http://registry.npm.taobao.org/`

6. 创建脚本文件 RN.sh（如下）


{% highlight css %}


NODE_VERSION=`node -v | cut -d'v' -f 2`

wget http://npm.taobao.org/mirrors/node/v$NODE_VERSION/node-v$NODE_VERSION.tar.gz

rm -rf ~/.node-gyp
mkdir ~/.node-gyp

tar zxf node-v$NODE_VERSION.tar.gz -C ~/.node-gyp
mv ~/.node-gyp/node-v$NODE_VERSION ~/.node-gyp/$NODE_VERSION

printf "9\n">~/.node-gyp/$NODE_VERSION/installVersion


{% endhighlight %}


7. 执行RN.sh

8. 初始化项目 `npm install -g react-native-cli`   `react-native init AwesomeProject`

Tips:我在安装的时候发现brew的node版本高于淘宝镜像版本 自己手动切换的node版本。（可以用n切换也可以用nvm切换，）

`npm install -g n`  `n v5.4.0`

维持翻墙状态2分钟初始完成

（总体思路就是自己下载node-gyp源码, 就酱紫）



