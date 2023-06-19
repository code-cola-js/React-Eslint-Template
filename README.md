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
        "accessor-pairs": 2, 
        "arrow-spacing": [2, { 
          "before": true, 
          "after": true 
        }],
        "block-spacing": [2, "always"], 
        "brace-style": [0, "1tbs", { 
          "allowSingleLine": true
        }],
        "camelcase": 2, 
        "comma-dangle": [0, "never"], 
        "comma-spacing": [2, { 
          "before": false,
          "after": true
        }],
        "comma-style": [2, "last"], 
        "constructor-super": 2, 
        "dot-location": [2, "property"], 
        "eol-last": 2, 
        "generator-star-spacing": [2, { 
          "before": true,
          "after": true
        }],
        "handle-callback-err": [2, "^(err|error)$"], 
        "jsx-quotes": [2, "prefer-double"], 
        "key-spacing": [2, { 
          "beforeColon": false,
          "afterColon": true
        }],
        "keyword-spacing": [2, { 
          "before": true,
          "after": true
        }],
        "new-cap": [2, { 
          "newIsCap": false,
          "capIsNew": false
        }],
        "new-parens": 2, 
        "no-array-constructor": 2, 
        "no-caller": 2, 
        "no-console": "off", 
        "no-debugger": "off",
        "no-class-assign": 2,
        "no-cond-assign": [2, "except-parens"], 
        "no-const-assign": 2, 
        "no-control-regex": 0, 
        "no-delete-var": 2, 
        "no-dupe-args": 2, 
        "no-dupe-class-members": 2, 
        "no-dupe-keys": 2, 
        "no-duplicate-case": 2, 
        "no-empty-character-class": 2,
        "no-empty-pattern": 2, 
        "no-eval": 2, 
        "no-ex-assign": 2, 
        "no-extend-native": 2,
        "no-extra-bind": 2, 
        "no-extra-boolean-cast": 2, 
        "no-extra-parens": [2, "functions"],
        "no-fallthrough": 2,
        "no-floating-decimal": 2, 
        "no-func-assign": 2, 
        "no-implied-eval": 2,  
        "no-inner-declarations": [2, "functions"],
        "no-invalid-regexp": 2, 
        "no-irregular-whitespace": 2, 
        "no-iterator": 2, 
        "no-label-var": 2,
        "no-labels": [2, {
          "allowLoop": false,
          "allowSwitch": false
        }],
        "no-lone-blocks": 2, 
        "no-mixed-spaces-and-tabs": 2,
        "no-multi-spaces": 2, 
        "no-multi-str": 2, 
        "no-multiple-empty-lines": [1, { 
          "max": 2
        }],
        "no-native-reassign": 2, 
        "no-negated-in-lhs": 2, 
        "no-new-object": 2,
        "no-new-require": 2,
        "no-new-symbol": 2, 
        "no-new-wrappers": 2, 
        "no-obj-calls": 2,
        "no-octal": 2, 
        "no-octal-escape": 2,
        "no-path-concat": 2,
        "no-proto": 2, 
        "no-redeclare": 2, 
        "no-regex-spaces": 2,
        "no-return-assign": [2, "except-parens"], 
        "no-self-assign": 2,
        "no-self-compare": 2,
        "no-sequences": 2, 
        "no-shadow-restricted-names": 2,
        "no-spaced-func": 2, 
        "no-sparse-arrays": 2,
        "no-this-before-super": 2,
        "no-throw-literal": 2, 
        "no-trailing-spaces": 0,
        "no-undef": 2, 
        "no-undef-init": 2,
        "no-unexpected-multiline": 2, 
        "no-unmodified-loop-condition": 2,
        "no-unneeded-ternary": [2, { 
          "defaultAssignment": false
        }],
        "no-unreachable": 2, 
        "no-unsafe-finally": 2,
        "no-unused-vars": [2, { 
          "vars": "all",
          "args": "none"
        }],
        "no-useless-call": 2, 
        "no-useless-computed-key": 2,
        "no-useless-constructor": 2,
        "no-useless-escape": 0,
        "no-whitespace-before-property": 0,
        "no-with": 2,
        "one-var": [2, "never"], 
        "operator-linebreak": [2, "after", { 
          "overrides": {
            "?": "before",
            ":": "before"
          }
        }],
        "padded-blocks": [0, "never"], 
        "quotes": [2, "double", { 
          "avoidEscape": true,
          "allowTemplateLiterals": true
        }],
        "semi": [0, "never"], 
        "semi-spacing": [0, {
          "before": false,
          "after": true
        }],
        "space-before-blocks": [2, "always"],
        "space-before-function-paren": [0, "never"], 
        "space-in-parens": [2, "never"],
        "space-infix-ops": 2, 
        "space-unary-ops": [2, {
          "words": true,
          "nonwords": false
        }],
        "spaced-comment": [2, "always", { 
          "markers": ["global", "globals", "eslint", "eslint-disable", "*package", "!", ","]
        }],
        "template-curly-spacing": [0, "never"], 
        "use-isnan": 2, 
        "valid-typeof": 2, 
        "wrap-iife": [2, "any"], 
        "yield-star-spacing": [2, "both"], 
        "yoda": [2, "never"], 
        "prefer-const": 2, 
        "object-curly-spacing": [0, "always", {
          "objectsInObjects": false
        }],
        "array-bracket-spacing": [0, "never"],
        "linebreak-style": 0, 
        "no-var": 2, 
        "no-extra-semi": 0, 
        "no-unsafe-negation": 2,
        "curly": 2, 
        "eqeqeq": 2, 
        "no-else-return": 2, 
        "no-unused-expressions": [2, { 
          "allowShortCircuit": true,
          "allowTernary": true
        }],
        "no-useless-return": 2,
        "consistent-this": 0, 
        "function-paren-newline": [2, "multiline"], 
        "implicit-arrow-linebreak": [2, "beside"], 
        "indent": [2, 2, {
          "SwitchCase": 1
        }],
        "lines-between-class-members": 2,
        "max-depth": 2, 
        "no-inline-comments": 2, 
        "no-mixed-operators": [2, { 
          "groups": [
            ["*", "/", "%", "**"],
            ["&", "|", "^", "~", "<<", ">>", ">>>"],
            ["==", "!=", "===", "!==", ">", ">=", "<", "<="],
            ["&&", "||"],
            ["in", "instanceof"]
          ],
          "allowSamePrecedence": true
        }],
        "padding-line-between-statements": [ 
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
