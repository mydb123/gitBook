---
title: 使用React
---
## 安装包
1. 运行 `cnpm i react react-dom -s` 安装包
    + react: 专门用来创建组件和虚拟DOM的,同时组件的生命周期都在这个包中
    + react-dom: 专门进行DOM操作的,最主要的应用场景,就是`ReactDOM.render()`
2. 在`index.html`页面中，创建容器：

   ```html
   <!-- 容器，将来，使用 React 创建的虚拟DOM元素，都会被渲染到这个指定的容器中 -->
   <div id="app"></div>
   ```

3. 导入 包：
 
   ```js
   //index.js
   import React from 'react' //创建组件,虚拟DOM元素

   import ReactDOM from 'react-dom'  // 把创建好的组件和虚拟dom放在页面上展示的
   ```

4. 创建虚拟DOM元素：

   ```jsx
   // 这是 创建虚拟DOM元素的 API    <h1 title="啊，五环" id="myh1">你比四环多一环</h1>
   //  第一个参数： 字符串类型的参数，表示要创建的标签的名称
   //  第二个参数：对象类型的参数， 表示 创建的元素的属性节点
   //  第三个参数： 子节点
   const myh1 = React.createElement('h1', { title: '啊，五环', id: 'myh1' }, '你比四环多一环')
   ```


5. 渲染：

   ```js
   // 3. 渲染虚拟DOM元素
   // 参数1： 表示要渲染的虚拟DOM对象
   // 参数2： 指定容器,注意：这里不能直接放 容器元素的Id字符串，需要放一个容器的DOM对象
   ReactDOM.render(myh1, document.getElementById('app'))
   ```

   ​