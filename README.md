## vue-answer是什么？
    * 答案（answer）--找你所问，问你所需
    * 在答案，你可以找到任何你需要的解决办法
    * 在答案，你可以轻易找到曾经历相同困境的朋友
    * 答案，你的知识解决方案宝库，披荆斩棘的同路人

### 结果
    * 作为一名前端，手把手演示，如何制作一款有点创意，有点逼格的手机应用。
    * UI界面我尽力
    * 用户体验会虚谁？
### 过程
    *  了解项目如何创建以及搭建对应结构。
        - 初始化项目
        - 搭建基础router（路由）
        - 搭建基础vuex（状态管理）
        - 搭建基础axios（数据请求）

    *  在上一条的基础上，对结构进行修改
        - 修改router,使router更棒更便于管理。转场动画，平移、淡入淡出、缩放...
        - 修改vuex,使页面数据更易于开发、维护
        - 修改axios，使api接口能够被统一管理，并且每一个调用的地方又能执行其具体的操作

    *  到了这一步，项目结构在不断改进过程中已经棒棒的了，基本可以完成任何后续操作。☺
    *  前面我们都是在浏览器中运行，接下来使用cordova编译出可在手机上运行的android,ios APP *

### 展示
  ![image](https://github.com/ifredom/vue-answer/raw/master/test/testsrc/1.png)
  ![image](https://github.com/ifredom/vue-answer/raw/master/test/testsrc/2.png)
### 下载安装
  ![image](https://github.com/ifredom/vue-answer/raw/master/test/testsrc/ifredom-answoe-code.png)
### 技术前提
        vue(熟练) + vuex(一般) + axios(一般)
        ES6（一般）
        webpack（一般）
        nodejs(了解)
### 开发环境
    1. node v6.9.4
    2. cnpm v4.5.0
    3. npm v3.10.10

### 使用方法：
    // 安装好node之后，克隆项目，打开cmd进入项目目录
    // 安装依赖
    npm install

    // 运行
    npm run dev

### 上线编译：
    npm run build
    // 生成的dist文件夹放在服务器即可正常访问

### development progress log
        changelog-4.
            （正在进行中...）
        changelog-4.
            1）上一节home页面制作完成，但是app的显通常都有导航栏，我设置为导航栏另外两个为person和my。
            2） 制作出person和my页面，并且添加上导航跳转，也就是footer中3个栏目的跳转。
            3）此时设定为头部和服用组件，但是我想以后成型的app拥有搜索功能，所以主页home我将头部改为搜索栏。
            4）制作出home页面搜索栏。分析一下，home页（栏目一）顶部是搜索栏，市面上app点击搜索栏都是跳转到另外一个页面
            5）所以制作出search.vue.
        changelog-2.
            1）上一节，搭建好了根路由和登录页面，项目启动后，自动进入跟路由app.vue，而此时的默认组件为login,所以自动跳转到了登录界面。随意设定一个密码，登录成功后将跳转到应用的主页面。主页面设定为home组件
            2）此时页面的主体结构需要进行划分，划分为 content + footer.
            3) 制作出home.vue页面.
            4) 在制作home的过程中，显然头部和底部应该是可以重用的，所以制作为可复用组件（初学者，在此步骤可以先不用管组件化，也不用管底部跳转，只需将页面做出来）
            5）home页面制作完成后，将头部和底部改为可服用组件，并链接上路由跳转，存放在components/common/中统一管理可复用组件
        changelog-1.
            1）使用vue-cli初始化项目，页面全空.
            2）此时设计项目结构，计划使用router控制路由，vuex控制页面中状态变化，使用axios进行数据请求
            3) 第一步搭建路由，确定项目结构。路由统一控制在router/router.js.并确立app.vue作为页面的根路由组件.
            4) 新建页面app.vue，此页面仅仅作为根路由，不包含任何内容。根路由有了，此时计划将登录页面作为默认页面，在路由中配置登录页为app.vue的默认组件（页面），并写出页面login.vue。
            5）再次访问地址时，就会自动跳转到登录页面（默认页面）。登录时会调用接口requestLogin,我统一在api/api.js中进行管理，并且在api管理具体地址，此处我设置的是空''*[]:
               因此调用接口时，调用的地方(loin.vue)只需要传入对应参数，执行具体的逻辑操作（跳转到home），而api的统一管理请求地址。顺便加了个进度条NProgress
            6) 由于登录接口的地址我写了个self ajax adress,显然是不存在这样的服务器请求地址的，所以会返回404（找不到服务器地址），不过我依然强行跳转到了home
###  support browser
        IE 10+
        Andorid 4.1+
        IOS 7+
### 项目结构
    .
    -- build                            // 项目构建相关代码
    |   |-- build.js                     // 生产环境构建代码
    |   |-- check-version.js             // 检查 node、npm 等版本
    |   |-- dev-client.js                // 热重载相关
    |   |-- dev-server.js                // 构建本地服务器
    |   |-- utils.js                     // 构建工具相关
    |   |-- webpack.base.conf.js         // webpack 基础配置（出入口和 loader）
    |   |-- webpack.dev.conf.js          // webpack 开发环境配置
    |   |-- webpack.prod.conf.js         // webpack 生产环境配置
    |-- config                           // 项目开发环境配置
    |   |-- dev.env.js                   // 开发环境变量
    |   |-- index.js                     // 项目一些配置变量（开发环境接口转发将在此配置）
    |   |-- prod.env.js                  // 生产环境变量
    |   |-- test.env.js                  // 测试环境变量
    |-- src                              // 源码目录
    |   |-- api                          // ajxa请求接口地址
    |   |-- components                   // vue 公共组件
    |   |-- page                         // 页面
    |   |-- image                        // 图片
    |   |-- style                        // CSS样式
    |   |-- router                       // 路由
    |   |-- vuex                         // vuex 的组件状态统一管理
    |   |-- App.vue                      // 页面入口文件
    |   |-- main.js                      // 程序入口文件，加载各种公共组件
    |-- static                           // 静态文件，比如一些图片，json数据等
    |-- test                             // 自动化测试相关文件
    |-- .babelrc                         // ES6语法编译配置
    |-- .editorconfig                    // 定义代码格式
    |-- .eslintignore                    // ESLint 检查忽略的文件
    |-- .eslistrc.js                     // ESLint 文件，eslint检测规则配置，如需更改，在此添加
    |-- .gitignore                       // git 上传需要忽略的文件
    |-- README.md                        // 项目说明
    |-- index.html                       // 入口页面
    |-- package.json                     // 项目基本信息
    .
