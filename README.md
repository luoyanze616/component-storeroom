## 如何发布至npm
首先修改package.json里version的版本号，然后执行npm run build打包，不需要的文件可在.gitignore和.npmignore文件中填写即过滤不会上传
命令行登录npm：npm login，输入username，password，邮箱
执行：npm publish，查看命令行成功信息是否是修改过的版本号
完成

## 如何调用npm已发布的组件库
说明：components.json记录将要打包的功能模块名称和路径
在需要引入组件库的项目中执行npm install component-storeroom -S
在package.json文件中查看component-storeroom是否存在且版本号与之前更新或发布的一致，如不一致重新安装，不能覆盖的话就npm uninstall
在需要使用的项目中的main.js中写入
import Vue from 'vue';
import ComponentStoreRoom from 'component-storeroom';
import 'component-storeroom/lib/theme/index.css';
import App from './App.vue';

Vue.use(ComponentStoreRoom);

new Vue({
  el: '#app',
  render: h => h(App)
});
注意：样式文件需要单独引入。

其他更多的使用方法可直接install项目，npm run dev跑起来后直接查看md文档或example演示

## 按需加载
借助babel插件`babel-plugin-component`实现

详细查看点击下方链接
[segmentFault](https://segmentfault.com/a/1190000015884948)

## markdown编写说明文档

详细查看点击下方链接
[segmentFault](https://segmentfault.com/a/1190000016342795)

## 为组件库增加单元测试
详细查看点击下方链接
[segmentFault](https://segmentfault.com/a/1190000017970919)
