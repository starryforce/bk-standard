
# 商品
国别 + 品牌英文名称 + 品牌中文名称 + 中文名称 + 商品名称 + 规格
# 项目
## 文件夹、文件
To do 
## 单文件组件
To do 

# HTML
HTML 标签命名用名词，如 head、nav（导航）

# CSS
* CSS 的类名可以用名词、形容词、表示意图和状态的动词/动词短语
* 使用**中划线**连接多个单词，如 list、color-red、clear-fix、visited（访问过的）、loading（加载中）
* 尽量减少复杂的 child 伪类选择器，而是使用类

# JavaScript
* 变量命名 camelCase（驼峰命名法，第一个单词首字母小写、第二个单词的首字母大写）
* 类名，命名空间 PascalCase（大驼峰命名法，单词首字母**均大写**）
## 变量：
* 变量可以用名词、形容词、表示意图和状态的动词及动词短语
* 对于数组，命名中应该包含 Array、List 等，也可用名词的复数形式，如 Orders、Users
* 对于遍历数组中的元素可使用 element、item、listItem、it、iterator 等命名，如 forEach、filter
* 布尔类型的变量一般以 is、has 开头，如 isActived
## 函数：
* 一般使用动词、动宾短语、动词过去式、动词进行时来命名函数，动宾短语通常是一个动词+函数返回值/参数的名称（getUsers、sendMessage）
* 对于请求数据的函数，一般可用get等开头来命名，如 getUserByTel、getOrders
* 对于上传、保存用户数据的函数，一般可用 set/send 等开头来命名，如 setToken、setUserInfo
* 返回布尔类型的函数可以 is、has 开头，如 hasKey 
* 函数的参数命名参考变量章节
* 在传递多个不同类型的参数时，使用对象而不是数组

    不推荐 
```js
        createCanvas(arr)
        // arr[0]--高度  
        // arr[1]--宽度
```
    推荐
```js
        createCanvas(height,width)
        createCanvas({height,width})
```
# Vue 

## 内容：
* 有意义的: 不过于具体，也不过于抽象
* 简短: 2 到 3 个单词
* 具有可读性: 以便于沟通交流

## 格式方面：
### 没有子组件的单文件组件
文件名：`PascalCase.vue`

路径：`components/PascalCase.vue`

### 有子组件的单文件组件
文件结构：

    components
		  AppHeader
		            index.vue
		            AppHeaderChild.vue
#### 引用路径：
```js
    // bad
    import AppHeader from './AppHeader/AppHeader.vue'

    // bad
    import AppHeader from './AppHeader/index.vue'

    // good
    import AppHeader from './app-header'
```
#### 引用命名：
```js
    // bad
    import appHeader from './app-header'

    // good
    import AppHeader from './app-header'
```
#### 模板标签：
```html
    // bad
    <AppHeader><AppHeader />

    // good
    <app-header><app-header />
```
Vue组件注册的名称是没有限制的，组件引用采用帕斯卡命名法。

Vue组件的模板解析是有限制的，组件模板采用短横线命名法。

PascalCase 是最通用的 声明约定 而 kebab-case 是最通用的 使用约定。

kebab-case，camelCase，或 PascalCase。

* 局部变量：以下划线开头
* 属性、方法名：驼峰命名（camelCase）
* class、id：中划线命名（kebab-case）
* 文件夹：中划线命名（kebab-case）

## Vuex
在 vuex 中，action 一般推荐以 get 开头来命名、mutations 以 set 开头

参考资料：
[一篇关于Vue解析规则的分析文章](https://jingsam.github.io/2016/10/30/vue-components-naming.html)