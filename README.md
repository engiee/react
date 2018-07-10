## Quick Start

在自己的机器上调试：

1. 保证node版本5.3+，npm版本3.3+
2. clone下来后，`npm install`，安装必要的依赖
3. `npm run dev`，启动webpack-dev-server，打开浏览器`http://localhost:8080`查看效果。默认是debug模式，不会请求后端接口，所有数据都是mock的，相关配置见[src/config.js](src/config.js)
4. 如果有必要的话可以把logLevel设置为debug（见[src/config.js](src/config.js)），会输出详细的debug日志，打开chrome的console就可以看到。

用在自己的项目中：

1. 保证node版本5.3+，npm版本3.3+
2. clone下来后，`npm install`，安装必要的依赖
3. 参考[src/menu.js](src/menu.js)，按自己的需要配置侧边栏和顶部菜单
4. 修改[src/index.js](src/index.js)中的路由表，保证和menu.js中的菜单项一致，否则可能404
5. 如果要用DBTable组件的话，参考[src/schema](src/schema)下的例子，编写自己的querySchema和dataSchema文件。在路由表中配置DBTable组件时，要把表名作为props传入，类似`<Route path="option1" tableName="test" component={DBTable}/>`。
6. 修改[src/config.js](src/config.js)中相关配置，比如项目名、footer、单点登录等等。
7. `npm run prod`，编译js文件，然后将dist目录下的所有js/css/html文件拷贝到自己的工程中，前端的工作就完成了。一般会有一个index.html，一个bundle.min.css，以及多个js文件，跟是否使用动态路由有关。
8. 开发后端接口，接口规范见[这里](docs/Ajax.md)。如果是java后端，可以使用[这个工具](https://github.com/jiangxy/react-java-goos)帮你生成。
9. 启动你的web服务，访问`index.html`查看效果。

其他一些命令:

1. `npm run eslint`/`npm run stylelint`/`npm run lesshint`，一些lint工具。
2. `npm run clean`，删除dist目录下的bundle*.js。
