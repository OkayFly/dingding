[使用electron封装网页版钉钉](https://github.com/weiyinfu/dingding)

# 功能说明
1. 使用electron封装网页版钉钉并加以定制，获取客户端一样的体验
2. 解决了网页版钉钉内容区域无法最大化的问题
3. 窗口按钮：最大化、最小化、关闭
4. 消息通知，可以显示消息详情

# 使用
* 下载源码：`git clone git@github.com:weiyinfu/dingding.git`
* 安装依赖：`npm install` 
* 开发：`make dev`
* 编译：`make build`
* 打包：`make package`
* 安装到本地：`make install`

# 代码风格
1. 能用CSS解决的问题就不要用JS
2. 一切功能扩展都在plugin目录下，每个功能扩展应该互相独立，完全解耦。想删除某个功能只需要删除一个文件即可。main.js会自动扫描plugin目录下的全部文件，将以Server.js结尾的文件调用它们的函数，将不以Server.js结尾的文件注入到浏览器中。
3. 在所有的进程中，如果需要访问图片资源或者其他资源，请通过`path.join(app.getAppPath(), './icon/32x32.png')`的方式来获取，因为打包之后相对的目录结构不能保证一致
4. 安装只需要四个文件
   * 安装脚本：install.sh
   * 可执行程序：dist/dingding 1.0.0.Appimage
   * 图标：dingding.ico
   * dingding.desktop

tar -czf dingding.tar.gz install.sh dingding.ico dingding.desktop -C dist "dingding 1.0.0.AppImage"
# 参考资料 
* [nashaofu的electron钉钉](https://github.com/nashaofu/dingtalk)
* [微信electron版](https://ywnz.com/linuxjc/2609.html)
* [electron中文教程](https://www.w3cschool.cn/electronmanual/)
* [electron官方教程](https://electron.atom.io/docs/)
* [electronjs.org/community#boilerplates](https://electronjs.org/community#boilerplates) - sample starter apps created by the community
* [electron/electron-quick-start](https://github.com/electron/electron-quick-start) - a very basic starter Electron app
* [electron/simple-samples](https://github.com/electron/simple-samples) - small applications with ideas for taking them further
* [electron/electron-api-demos](https://github.com/electron/electron-api-demos) - an Electron app that teaches you how to use Electron
* [hokein/electron-sample-apps](https://github.com/hokein/electron-sample-apps) - small demo apps for the various Electron APIs