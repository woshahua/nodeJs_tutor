## use nodeJs and express to build blog

### install
1. npm install -g express-generator (g: global)
2. express -e blog

### File
- app.js: 入口文件，启动服务
- package.json: 存储依赖模块, 通过npm install来下载相关模块
- node_module: 存放npm安装的模块
- public: 存放image,css,js等文件, 就是装网站门面的地方。
- routes: 路由文件$
- views: 网站门面
- bin: 存放可执行文件

### code
- `var app = express` 生成express实例
- `app.set("views", path.join(dirname, "views"))` 设置views文件夹为存放视图文件的目录. dirname为全局变量，即当前文件夹。
- `app.set("view engine", "ejs")`
- `app.use(favicon(dirname + "/public/favicon.ico"))` 设置favicon图标.
- `module.exports = app` 导出app实例供其他模块调用.


### 路由规则
express封装了多种http请求方式, 在这里主要用到get和post. app.get()和app.post()的第一个参数都为请求的路径, 第二个参数为处理请求的回调函数. 回调函数有两个参数分别为req和res.

- 当访问localhost:3000/sbsbdasb时路由会返回404 no found的error, 原因就是程序中并没有这条路由规则. 做一下改正后就会返回“hello world !”

```javascript
app.get("/sbsbdasb", function(req, res){
  res.send("hello world!");
});
```
