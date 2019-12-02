# Z-File

此项目是一个在线文件目录的程序, 支持各种对象存储和本地存储, 使用定位是个人放常用工具下载, 或做公共的文件库. 不会向多账户方向开发.

前端基于 [h5ai](https://larsjung.de/h5ai/) 的原有功能使用 Vue 重新开发了一遍. 后端采用 SpringBoot, 数据库采用内嵌数据库.

预览地址: [http://zfile.jun6.net](http://zfile.jun6.net)

## 系统特色

* 内存缓存 (免安装)
* 内存数据库 (免安装)
* 个性化配置
* 自定义目录的 header 和 footer 说明文件
* 文件夹密码
* 支持在线浏览文本文件, 视频, 图片, 音乐.
* 文件/目录二维码

## 快速开始


安装 JDK 1.8 : 

```bash
yum instal -y java # 适用于 Centos 7.x
```

> 其他系统的 JDK 安装教程, 后续我也都会补上. 大家也可执行搜索安装方式, 应该不是很难.

下载项目:

```bash
wget https://github.com/zhaojun1998/zfile/releases/download/0.1/zfile-0.1.jar
```

启动项目:

```bash
java -jar zfile-0.1.jar

## 高级启动
java -jar zfile-0.1.jar --server.port=18777
```

`--server.port` 为指定端口, 默认为 `8080`

其他参数, 后面我会详细补充至文档, 最晚本周六日.

## 运行环境

* JDK: `1.8`
* 缓存: `caffeine/redis`
* 数据库: `h2/mysql`

## 常见问题

### 缓存

缓存默认支持 `caffeine` 和 `redis`, 前者为内存缓存, 无需安装, 但后者相对性能更好.

### 数据库

缓存默认支持 `h2` 和 `mysql`, 前者为嵌入式数据库, 无需安装, 但后者相对性能更好.


### 默认路径

默认 H2 数据库文件地址: `~/.zfile/db/`, `~` 表示用户目录, windows 为 `C:/Users/用户名/`, linux 为 `/home/用户名/`, root 用户为 `/root/`


### 头尾文件和加密文件

- 目录头部显示文件名为 `header.md`
- 目录底部显示文件名为 `footer.md`
- 目录需要密码访问, 添加文件 `password.txt` (无法拦截此文件被下载, 但可以改名文件)

## TODO

- 全局搜索功能
- 文本预览更换更好用的编辑器
- 后台支持上传、编辑、删除等操作
- API 支持
- 更方便的部署方式
