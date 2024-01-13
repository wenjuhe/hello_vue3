# 编写App组件
Vite 项目中, index.html 是项目的入口文件, 在项目最外层.
加载 index.html 后, Vite 解析 <script type="module" src="xxx"> 指向的 JavaScript
Vue3 中是通过 createApp 函数创建一个应用实例

# OptionsAPI与CompositionAPI

# setup与OptionsAPI
data和methods可以同setup同时存在

# setup语法糖
npm i vite-plugin-vue-setup-extend -D
文件名 与 组件名

# ref对比reactive
宏观角度看:
1. ref 用来定义: 基本类型数据, 对象类型数据
2. reactive 用来定义: 对象类型数据
区别:
1. ref 创建的变量必须使用 .value (可以使用 volar 插件自动添加 .value)
2. reactive 重新分配一个新对象, 会失去响应式 (可以使用 object.assign 去整体替换)   ===> reactive的局限性
使用原则:
1. 若需要一个基本类型的响应式数据, 必须使用 ref
2. 若需要一个响应式对象, 层级不深, ref, reactive 都可以
3. 若需要一个响应式对象, 且层级较深, 推荐使用 reactive
