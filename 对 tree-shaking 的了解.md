
Dead Code 一般具有以下几个特征:

•代码不会被执行，不可到达

•代码执行的结果不会被用到

•代码只会影响死变量（只写不读）




ES6 module 特点：

•只能作为模块顶层的语句出现

•import 的模块名只能是字符串常量

•import binding 是 immutable的




**1.虽然生产模式下默认开启，但是由于经过 babel 编译全部模块被封装成 IIFE**

**2.IIFE 存在副作用无法被 tree-shaking 掉**

**3.需要配置 { module: false }和 sideEffects: false**

**rollup只处理函数和顶层的import/export变量，不能把没用到的类的方法消除掉javascript动态语言的特性使得静态分析比较困难**

**前端中的tree-shaking可以理解为通过工具"摇"我们的JS文件，将其中用不到的代码"摇"掉，是一个性能优化的范畴。具体来说，在 webpack 项目中，有一个入口文件，相当于一棵树的主干，入口文件有很多依赖的模块，相当于树枝。实际情况中，虽然依赖了某个模块，但其实只使用其中的某些功能。通过 tree-shaking，将没有使用的模块摇掉，这样来达到删除无用代码的目的。**

