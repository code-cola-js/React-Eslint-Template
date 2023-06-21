## 安装依赖

这些依赖是与 JavaScript 和 React.js 前端开发相关的工具和库。下面是每个依赖的功能和作用：

1. **@babel/core**: Babel 是一个 JavaScript 编译器，@babel/core 是 Babel 的核心模块，用于将新版本的 JavaScript 代码转换为向后兼容的旧版本代码，以便在不支持最新语法和特性的环境中运行。

2. **@babel/eslint-parser**: 这个依赖是 Babel 的 ESLint 解析器插件，用于在 ESLint 中解析 Babel 转换后的代码，使得 ESLint 可以理解并对其进行静态代码分析和规则检查。

3. **@babel/plugin-transform-react-jsx**: 这是一个 Babel 插件，用于将 JSX 语法转换为普通的 JavaScript 函数调用或对象表示，使得 React 组件可以在浏览器中运行。

4. **@babel/preset-env**: 这个 Babel 预设(preset)用于根据目标运行环境自动确定需要的转换和插件，以确保代码在目标环境中的兼容性。

5. **eslint**: ESLint 是一个用于检查和修复 JavaScript 代码的静态分析工具，它帮助开发人员遵循一致的编码风格和规范，以减少错误和提高代码质量。

6. **eslint-plugin-react**: 这是一个 ESLint 插件，提供了用于检查和维护 React.js 代码规范的规则集。

7. **eslint-plugin-react-hooks**: 这个 ESLint 插件为 React 的 Hook API 提供了规则和建议，以帮助开发人员编写正确和一致的 Hook 使用方式。

8. **@babel/plugin-proposal-private-property-in-object**: 这是一个 Babel 插件，用于将私有属性的提案转换为普通的 JavaScript 代码，使得私有属性可以在浏览器中运行。

这些依赖的组合通常用于支持使用最新的 JavaScript 语法和特性，同时进行代码风格检查和规范，并确保 React.js 组件的正确性和性能。

```shell
npm install --save-dev @babel/core @babel/eslint-parser @babel/plugin-transform-react-jsx @babel/preset-env eslint @babel/plugin-proposal-private-property-in-object eslint-plugin-react eslint-plugin-react-hooks
```

### 配置 `Babel` `.babelrc`

```json
{
    "presets": [
      "@babel/preset-env"
    ],
    "plugins": [
      "@babel/plugin-transform-react-jsx"
    ]
  }
```

### 配置 `ESLint` `.eslintrc.json`

```json
{
  "parser": "@babel/eslint-parser",
    "extends": [
      "eslint:recommended",
      "plugin:react/recommended"
    ],
    "plugins": [
      "react",
      "react-hooks"
    ],
    "parserOptions": {
      "ecmaFeatures": {
        "jsx": true
      }
    },
    "globals": {
      "document": true,
      "test": true,
      "expect": true
    },
    "rules": {
      // 在这里添加你的自定义规则
        "accessor-pairs": 2, // 强制 getter 和 setter 在对象中成对出现
        "arrow-spacing": [2, { // 强制箭头函数的箭头前后使用一致的空格
          "before": true,
          "after": true
        }],
        "block-spacing": [2, "always"], // 禁止或强制在代码块中开括号前和闭括号后有空格
        "brace-style": [0, "1tbs", { // 强制在代码块中使用一致的大括号风格
          "allowSingleLine": true
        }],
        "camelcase": 2, // 强制使用骆驼拼写法命名约定
        "comma-dangle": [0, "never"], // 要求或禁止末尾逗号
        "comma-spacing": [2, { // 强制在逗号前后使用一致的空格
          "before": false,
          "after": true
        }],
        "comma-style": [2, "last"], // 强制使用一致的逗号风格
        "constructor-super": 2, // 要求在构造函数中有 super() 的调用
        "dot-location": [2, "property"], // 强制在点号之前和之后一致的换行
        "eol-last": 2, // 要求或禁止文件末尾存在空行
        "generator-star-spacing": [2, { // 强制 generator 函数中 *号周围使用一致的空格
          "before": true,
          "after": true
        }],
        "handle-callback-err": [2, "^(err|error)$"], // 要求回调函数中有容错处理
        "jsx-quotes": [2, "prefer-double"], // 强制在 JSX 属性中一致地使用双引号或单引号
        "key-spacing": [2, { // 强制在对象字面量的属性中键和值之间使用一致的间距
          "beforeColon": false,
          "afterColon": true
        }],
        "keyword-spacing": [2, { // 强制在关键字前后使用一致的空格
          "before": true,
          "after": true
        }],
        "new-cap": [2, { // 要求构造函数首字母大写
          "newIsCap": false,
          "capIsNew": false
        }],
        "new-parens": 2, // 要求调用无参构造函数时有圆括号
        "no-array-constructor": 2, // 禁用 Array 构造函数
        "no-caller": 2, // 禁用 arguments.caller 或 arguments.callee
        "no-console": "off", // 禁用 console
        "no-debugger": "off", // 禁用 debugger
        "no-class-assign": 2, // 禁止修改类声明的变量
        "no-cond-assign": [2, "except-parens"], // 禁止条件表达式中出现赋值操作符
        "no-const-assign": 2, // 禁止修改 const 声明的变量
        "no-control-regex": 0, // 禁止在正则表达式中使用控制字符
        "no-delete-var": 2, // 禁止删除变量
        "no-dupe-args": 2, // 禁止 function 定义中出现重名参数
        "no-dupe-class-members": 2, // 禁止类成员中出现重复的名称
        "no-dupe-keys": 2, // 禁止对象字面量中出现重复的 key
        "no-duplicate-case": 2, // 禁止出现重复的 case 标签
        "no-empty-character-class": 2, // 禁止在正则表达式中使用空字符集
        "no-empty-pattern": 2, // 禁止使用空解构模式
        "no-eval": 2, // 禁用 eval()
        "no-ex-assign": 2, // 禁止对 catch 子句的参数重新赋值
        "no-extend-native": 2, // 禁止扩展原生类型
        "no-extra-bind": 2, // 禁止不必要的 .bind() 调用
        "no-extra-boolean-cast": 2, // 禁止不必要的布尔转换
        "no-extra-parens": [2, "functions"], // 禁止不必要的括号
        "no-fallthrough": 2, // 禁止 case 语句落空
        "no-floating-decimal": 2, // 禁止数字字面量中使用前导和末尾小数点
        "no-func-assign": 2, // 禁止对 function 声明重新赋值
        "no-implied-eval": 2,  // 禁止使用类似 eval() 的方法
        "no-inner-declarations": [2, "functions"], // 禁止在嵌套的块中出现变量声明或 function 声明
        "no-invalid-regexp": 2, // 禁止 RegExp 构造函数中存在无效的正则表达式字符串
        "no-irregular-whitespace": 2, // 禁止不规则的空白
        "no-iterator": 2, // 禁用 **iterator** 属性
        "no-label-var": 2, // 不允许标签与变量同名
        "no-labels": [2, { // 禁用标签语句
          "allowLoop": false,
          "allowSwitch": false
        }],
        "no-lone-blocks": 2, // 禁用不必要的嵌套块
        "no-mixed-spaces-and-tabs": 2, // 禁止空格和 tab 的混合缩进
        "no-multi-spaces": 2, // 禁止使用多个空格
        "no-multi-str": 2, // 禁止使用多行字符串
        "no-multiple-empty-lines": [1, { // 禁止出现多行空行
          "max": 2
        }],
        "no-native-reassign": 2, // 禁止对原生对象赋值
        "no-negated-in-lhs": 2, // 禁止在 in 表达式中出现否定的左操作数
        "no-new-object": 2, // 禁用 Object 的构造函数
        "no-new-require": 2, // 禁止调用 require 时使用 new 操作符
        "no-new-symbol": 2, // 禁止 Symbolnew 操作符和 new 一起使用
        "no-new-wrappers": 2, // 禁止对 String，Number 和 Boolean 使用 new 操作符
        "no-obj-calls": 2, // 禁止把全局对象作为函数调用
        "no-octal": 2, // 禁用八进制字面量
        "no-octal-escape": 2, // 禁止在字符串中使用八进制转义序列
        "no-path-concat": 2, // 禁止对 __dirname 和 __filename 进行字符串连接
        "no-proto": 2, // 禁用 **proto** 属性
        "no-redeclare": 2, // 禁止多次声明同一变量
        "no-regex-spaces": 2, // 禁止正则表达式字面量中出现多个空格
        "no-return-assign": [2, "except-parens"], // 禁止在 return 语句中使用赋值语句
        "no-self-assign": 2, // 禁止自我赋值
        "no-self-compare": 2, // 禁止自身比较
        "no-sequences": 2, // 禁用逗号操作符
        "no-shadow-restricted-names": 2, // 禁止将标识符定义为受限的名字
        "no-spaced-func": 2, // 禁止 function 标识符和括号之间出现空格
        "no-sparse-arrays": 2, // 禁用稀疏数组
        "no-this-before-super": 2, // 禁止在构造函数中，在调用 super() 之前使用 this 或 super
        "no-throw-literal": 2, // 禁止抛出异常字面量
        "no-trailing-spaces": 0, // 禁用行尾空格
        "no-undef": 2, // 禁用未声明的变量，除非它们在 /*global */ 注释中被提到
        "no-undef-init": 2, // 禁止将变量初始化为 undefined
        "no-unexpected-multiline": 2, // 禁止出现令人困惑的多行表达式
        "no-unmodified-loop-condition": 2, // 禁用一成不变的循环条件
        "no-unneeded-ternary": [2, { // 禁止可以在有更简单的可替代的表达式时使用三元操作符
          "defaultAssignment": false
        }],
        "no-unreachable": 2, // 禁止在 return、throw、continue 和 break 语句之后出现不可达代码
        "no-unsafe-finally": 2, // 禁止在 finally 语句块中出现控制流语句
        "no-unused-vars": [2, { // 禁止出现未使用过的变量
          "vars": "all",
          "args": "none"
        }],
        "no-useless-call": 2, // 禁止不必要的 .call() 和 .apply()
        "no-useless-computed-key": 2, // 禁止在对象中使用不必要的计算属性
        "no-useless-constructor": 2, // 禁用不必要的构造函数
        "no-useless-escape": 0, // 禁用不必要的转义字符
        "no-whitespace-before-property": 0, // 禁止属性前有空白
        "no-with": 2, // 禁用 with 语句
        "one-var": [2, "never"], // 强制函数中的变量要么一起声明要么分开声明
        "operator-linebreak": [2, "after", { // 强制操作符使用一致的换行符风格
          "overrides": {
            "?": "before",
            ":": "before"
          }
        }],
        "padded-blocks": [0, "never"], // 要求或禁止块内填充
        "quotes": [2, "double", { // 强制使用一致的反勾号、双引号或单引号
          "avoidEscape": true,
          "allowTemplateLiterals": true
        }],
        "semi": [0, "never"], // 要求或禁止使用分号代替 ASI
        "semi-spacing": [0, { // 强制分号之前和之后使用一致的空格
          "before": false,
          "after": true
        }],
        "space-before-blocks": [2, "always"], // 强制在块之前使用一致的空格
        "space-before-function-paren": [0, "never"], // 强制在 function的左括号之前使用一致的空格
        "space-in-parens": [2, "never"], // 强制在圆括号内使用一致的空格
        "space-infix-ops": 2, // 要求操作符周围有空格
        "space-unary-ops": [2, { // 强制在一元操作符前后使用一致的空格
          "words": true,
          "nonwords": false
        }],
        "spaced-comment": [2, "always", { // 强制在注释中 // 或 /* 使用一致的空格
          "markers": ["global", "globals", "eslint", "eslint-disable", "*package", "!", ","]
        }],
        "template-curly-spacing": [0, "never"], // 强制模板字符串中空格的使用
        "use-isnan": 2, // 要求使用 isNaN() 检查 NaN
        "valid-typeof": 2, // 强制 typeof 表达式与有效的字符串进行比较
        "wrap-iife": [2, "any"], // 要求 IIFE 使用括号括起来
        "yield-star-spacing": [2, "both"], // 强制在 yield*表达式中* 周围使用空格
        "yoda": [2, "never"], // 要求或禁止 “Yoda” 条件
        "prefer-const": 2, // 要求使用 const 声明那些声明后不再被修改的变量
        "object-curly-spacing": [0, "always", { // 强制在大括号中使用一致的空格
          "objectsInObjects": false
        }],
        "array-bracket-spacing": [0, "never"], // 强制数组方括号中使用一致的空格
        "linebreak-style": 0, // 强制使用一致的换行风格
        "no-var": 2, // 要求使用 let 或 const 而不是 var
        "no-extra-semi": 0, // 禁止不必要的分号
        "no-unsafe-negation": 2, // 禁止对关系运算符的左操作数使用否定操作符
        "curly": 2, // 强制所有控制语句使用一致的括号风格
        "eqeqeq": 2, // 要求使用 === 和 !==
        "no-else-return": 2, // 禁止 if 语句中 return 语句之后有 else 块
        "no-unused-expressions": [2, { // 禁止出现未使用过的表达式
          "allowShortCircuit": true,
          "allowTernary": true
        }],
        "no-useless-return": 2, // 禁止多余的 return 语句
        "consistent-this": 0, // 当获取当前执行环境的上下文时，强制使用一致的命名
        "function-paren-newline": [2, "multiline"], // 强制在函数括号内使用一致的换行
        "implicit-arrow-linebreak": [2, "beside"], // 强制隐式返回的箭头函数体的位置
        "indent": [2, 2, { // 强制使用一致的缩进
          "SwitchCase": 1
        }],
        "lines-between-class-members": 2,  // 要求或禁止类成员之间出现空行
        "max-depth": 2, // 强制可嵌套的块的最大深度
        "no-inline-comments": 2, // 禁止在代码后使用内联注释
        "no-mixed-operators": [2, { // 禁止混合使用不同的操作符
          "groups": [
            ["*", "/", "%", "**"],
            ["&", "|", "^", "~", "<<", ">>", ">>>"],
            ["==", "!=", "===", "!==", ">", ">=", "<", "<="],
            ["&&", "||"],
            ["in", "instanceof"]
          ],
          "allowSamePrecedence": true
        }],
        "padding-line-between-statements": [ // 要求或禁止在语句间填充空行
          2,
          {"blankLine": "always", "prev": "block-like", "next": "*"},
          {"blankLine": "always", "prev": "let", "next": "expression"},
          {"blankLine": "always", "prev": "const", "next": "expression"},
          {"blankLine": "always", "prev": "let", "next": "block-like"},
          {"blankLine": "always", "prev": "const", "next": "block-like"},
          {"blankLine": "always", "prev": "expression", "next": "block-like"},
          {"blankLine": "always", "prev": "*", "next": "return"}
        ]
    }
}
```
