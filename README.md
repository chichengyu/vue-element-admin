# vue-element-admin

[码云](https://gitee.com/chichengyu/vue-element-admin)

#### 介绍

基于vue、element做的一个后台管理系统，默认打包出的是异步加载。这里也提供一个完整的包（包括依赖）[下载](https://share.weiyun.com/q66xenwH)即用，密码：`gzmpiy`  

vue-element-admin2.0 这里提供一个[下载(包括依赖)](https://share.weiyun.com/BqDHvccj)，密码：`pfah89`

说明：vue-element-admin2.0与之前的区别不大，只是重写了权限而已，全都有后台返回的权限菜单进行动态加载组件，不用在 `routesMap` 中进行添加路由了，但是位 `*` 路由不能删除，且后台返回的数据格式请参照 `权限格式数据.json`，vue-element-admin2.0需要特别注意：`后台返回的权限菜单中数据的 path 与 name` 必须与组件中对应组件目录名称一致，否则报错找不到组件

+ 注意：需要打开登录组件开启权限，默认 false 不开启
    ```
    // 1.
    var userInfo = {
      nickname: "超级管理员",
      username:'admin',
      roles: 1,
      token: "eyJhbGciOiJIUzI1NiJ9.eyJqd3Qt",
      "isAuth":false // true开启权限验证模式 ，false 不使用权限验证，默认无权限验证
    };
    this.$ls.set('userInfo',userInfo);
    this.success('登陆成功！');
    this.$router.push('/');
    return;
    
    // data: 登录成功后返回的数据
    data.isAuth = true;// 开发时可设置为false，便于快速开发界面
    ```
放开注释，即可。


#### 架构
架构说明

   + [Preview预览](http://xiaochiwz.gitee.io/thinkphp5.1-vue-ivew-admin)
   + [Element官网](https://element.eleme.cn/2.11/#/zh-CN/component/installation)
   + [Vue官网](https://cn.vuejs.org/v2/guide/)
   + [Webpack官网](https://www.webpackjs.com/)
   + [Easy Mock接口API](https://www.easy-mock.com/project/5bf4b1a323557c43607406bc)
   + [Element-component插件](https://www.npmjs.com/package/element-component)

#### 目录结构
目录  
```  
   │──dist            
   │──src             
   │  │──api             接口请求目录  
   │  │──assets          静态资源目录
   │  │──common          公共目录(如：公共函数,可直接修改，不影响打包后的文件)    
   │  │──components      组件目录  
   │  │──config          配置目录  
   │  │──lib             核心库目录  
   │  │──router          路由目录  
   │  │──store           vuex目录  
   │  │──views           视图目录  
   │  │──App.vue         根组件  
   │  │──index.html      模板文件    
   │  │──main.js         入口文件                  
   │  └──settings.js     配置文件
   │    ...
```

#### Getting started
```
# clone the project
git clone https://gitee.com/chichengyu/vue-element-admin.git

```
   
#### Build
```
# install dependency
npm install

# test development dev
npm run dev

# build
npm run build

# build test
npm run build:test

# watch
npm run watch
```

##### 打包问题
关于前端 ` npm run build `报错 ` ERROR in xxx.js from UglifyJs ` 错误问题，这因为 ` uglifyjs-webpack-plugin版本兼容问题造成的 `，解决方法：运行命令
```
npm uni uglifyjs-webpack-plugin -D

npm i uglifyjs-webpack-plugin@1 -D
```
当前版本是 ` 2.*版本 `，降低到 `1.* 版本`就可以了，再次打包成功

##### Preview
![输入图片说明](https://images.gitee.com/uploads/images/2020/0519/161814_3e6bf8d6_1508174.png "login.png")
![输入图片说明](https://images.gitee.com/uploads/images/2020/0807/151235_cc4d2d20_1508174.png "menu.png")
![输入图片说明](https://images.gitee.com/uploads/images/2020/0807/151245_9278a97a_1508174.png "auth.png")
![输入图片说明](https://images.gitee.com/uploads/images/2020/0807/151256_a6605153_1508174.png "user.png")

#### License
[MIT](https://opensource.org/licenses/MIT)
