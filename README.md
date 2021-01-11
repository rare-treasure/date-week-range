## date-week-range（周范围选择器）

> 基于 element-ui 2.x 开发，可依赖element-ui 2.x使用；也可独立使用，但要引入相应的样式

### 示例

https://cqe2b.csb.app/

### 目的

  - 项目需求，需要用到周选择器这功能，但没找到相应的组件库，故自己基于element-ui改造了个。


### 兼容

  - 当前版本暂不支持 vue3.0+；预计在1月初发布支持vue3.0+的第一版。

### 计划

  - ~~1.x 版本，支持 vue2（已完成）~~
  - 2.x 版本，将进行支持 vue3，计划通过
  date-week-range@next
  方式升级使用。

### 改动
  - 移除自动注入css，改用手动引入方式，以减少包的大小，避免出现样式覆盖情况；样式建议直接引入element-ui的[date-picker.css](https://unpkg.com/element-ui/lib/theme-chalk/date-picker.css)，或者引入[dist/date-picker.css](https://unpkg.com/data-week-range/dist/date-picker.css)；如果全局引入了element-ui 样式，则不需额外引入！
  
  - 新增esm模块，仅支持es6及以上的浏览器。

  ```javascript
    // 引入方式
    import dateWeekRange from 'date-week-range/dist/date-week-range.esm';

    // 如果要支持es5浏览器，请在vue.config.js文件，进行如下配置：
    <!-- vue.config.js -->
    module.exports = {
      <!-- 省略 -->
      transpileDependencies: ['date-week-range/dist', 'element-ui/packages', 'element-ui/src']
    }
  ```

### 安装 && 引入
- 如果不考虑浏览器兼容性，建议引入esm模块：
```javascript
import dateWeekRange from 'date-week-range/dist/date-week-range.esm'
```

> * #### 安装

``` bash
npm install date-week-range --save
```
> * #### 注册

##### 全局注册

```javascript
import dateWeekRange from 'date-week-range';
import Vue from 'vue';

// 引入样式；如果全局引入了element-ui 样式，则不需额外引入
// 推荐
import 'element-ui/lib/theme-chalk/date-picker.css'
// or
import 'date-week-range/dist/date-picker.css'

Vue.use(dateWeekRange);
```

##### 局部引入

```javascript
<script>
import dateWeekRange from 'date-week-range';
// 样式，建议在全局中引入；如果全局引入了element-ui 样式，则不需额外引入
// 推荐
import 'element-ui/lib/theme-chalk/date-picker.css'
// or
import 'date-week-range/dist/date-picker.css'

export default {
  components: {
    dateWeekRange
  }
}
</script>
```

##### 直接引入

```html
<!-- 引入样式；如果全局引入了element-ui 样式，则不需额外引入 -->
<!-- 推荐 -->
<link type="text/css" href="https://unpkg.com/element-ui/lib/theme-chalk/date-picker.css">
<!-- or -->
<link type="text/css" href="https://unpkg.com/date-week-range/dist/date-picker.css">
<script src="https://unpkg.com/date-week-range"></script>
```

> * #### 使用

```html
  <date-week-range 
    v-model="test" 
    ...
  >
  </date-week-range>
```

### 配置

组件配置和 [element-ui 中的DatePicker组件](https://element.eleme.cn/#/zh-CN/component/date-picker) type="daterange" 配置相同。
