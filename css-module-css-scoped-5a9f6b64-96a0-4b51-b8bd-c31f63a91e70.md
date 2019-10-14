# css module和css scoped的区别和理解

Reviewed: No
Status: Css

# css scoped

加了scoped 属性会自动添加一个唯一的属性 (比如 data-v-21e5b78) 为组件内 CSS 指定作用域。

## 原理：

通过 Webpack 调用 VueJS 中相应 Loader , 给组件HTML模板添加自定义属性 (Attribute) data-v-x, 以及给组件内CSS选择器添加对应的属性选择器 (Attribute Selector) [data-v-x], 达到组件内样式只能生效与组件内HTML的效果。

## 缺点：

并不能完全避免冲突，若全局有一个同名的类名，则会被影响。

### 添加属性。

# css mudule

CSS Modules 是一个流行的，用于模块化和组合 CSS 的系统。vue-loader 提供了与 CSS Modules 的一流集成，可以作为模拟 scoped CSS 的替代方案。

## 原理：

不是官方标准，也不是浏览器的特性，而是在构建步骤中对CSS类名选择器限定作用域的一种方式（通过hash实现类似于命名空间的方法）。类名是动态生成的，唯一的，并准确对应到源文件中的各个类的样式。

## 作用：

加入了局部作用域、依赖管理，这恰恰解决了最大的痛点。可以有效避免全局污染和样式冲突，能最大化地结合现有 CSS 生态和 JS 模块化能力。

### 修改类名。