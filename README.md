## Install Dependencies

These dependencies are tools and libraries related to JavaScript and React.js front-end development. The following is the function and role of each dependency:

1. **@babel/core**: Babel is a JavaScript compiler, and @babel/core is the core module of Babel, which is used to convert the new version of JavaScript code into backward compatible old version code, so that when it does not support Runs in an environment with the latest syntax and features.

2. **@babel/eslint-parser**: This dependency is Babel's ESLint parser plugin, which is used to parse the Babel-transformed code in ESLint, so that ESLint can understand and perform static code analysis and rule checking on it.

3. **@babel/plugin-transform-react-jsx**: This is a Babel plugin for converting JSX syntax into ordinary JavaScript function calls or object representations, allowing React components to run in the browser.

4. **@babel/preset-env**: This Babel preset (preset) is used to automatically determine the required transformations and plugins according to the target operating environment to ensure the compatibility of the code in the target environment.

5. **eslint**: ESLint is a static analysis tool for checking and repairing JavaScript code, which helps developers follow a consistent coding style and specification to reduce errors and improve code quality.

6. **eslint-plugin-react**: This is an ESLint plugin that provides a rule set for checking and maintaining React.js code specifications.

7. **eslint-plugin-react-hooks**: This ESLint plugin provides rules and suggestions for React's Hook API to help developers write correct and consistent Hook usage.

8. **@babel/plugin-proposal-private-property-in-object**: This is a Babel plugin for converting private property proposals into plain JavaScript code, so that private properties can run in the browser .

The combination of these dependencies is often used to support the use of the latest JavaScript syntax and features, while performing code style checks and norms, and ensuring the correctness and performance of React.js components.

```shell
npm install --save-dev @babel/core @babel/eslint-parser @babel/plugin-transform-react-jsx @babel/preset-env eslint @babel/plugin-proposal-private-property-in-object eslint-plugin-react eslint-plugin-react-hooks
```

### Configure `Babel` `.babelrc`

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

### Configure `ESLint` `.eslintrc.json`

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
      // Add your custom rules here
        "accessor-pairs": 2, // Forces getters and setters to be paired in the object
        "arrow-spacing": [2, { // Enforces consistent spacing before and after the arrow in arrow functions
          "before": true,
          "after": true
        }],
        "block-spacing": [2, "always"], // Disallows or enforces spaces inside of single line blocks
        "brace-style": [0, "1tbs", { // Enforces consistent brace style for blocks
          "allowSingleLine": true
        }],
        "camelcase": 2, // Enforces camelcase naming convention
        "comma-dangle": [0, "never"], // Disallows trailing commas in object literals
        "comma-spacing": [2, { // Enforces consistent spacing before and after commas
          "before": false,
          "after": true
        }],
        "comma-style": [2, "last"], // Enforces consistent comma style
        "constructor-super": 2, 
        "dot-location": [2, "property"], // Enforces consistent newlines before or after dots
        "eol-last": 2, 
        "generator-star-spacing": [2, { // Enforces consistent spacing around * operators in generator functions
          "before": true,
          "after": true
        }],
        "handle-callback-err": [2, "^(err|error)$"], // Enforces error handling in callbacks
        "jsx-quotes": [2, "prefer-double"], // Enforce the consistent use of either double or single quotes in JSX attributes
        "key-spacing": [2, { // Enforces consistent spacing between keys and values in object literal properties
          "beforeColon": false,
          "afterColon": true
        }],
        "keyword-spacing": [2, { // Enforces consistent spacing before and after keywords
          "before": true,
          "after": true
        }],
        "new-cap": [2, { // Enforces newlines between the operands of a ternary expression
          "newIsCap": false,
          "capIsNew": false
        }],
        "new-parens": 2, // Enforces parentheses when invoking a constructor with no arguments
        "no-array-constructor": 2, // no array constructor
        "no-caller": 2, // Disallows the use of arguments.caller or arguments.callee
        "no-console": "off", // Disallows console.log
        "no-debugger": "off", // Disallows debugger
        "no-class-assign": 2, // Disallows reassigning class members
        "no-cond-assign": [2, "except-parens"], // Disallows assignment operators in conditional expressions
        "no-const-assign": 2, // Disallows reassigning const variables
        "no-control-regex": 0, // Disallows control characters in regular expressions
        "no-delete-var": 2, // Disallows deleting variables
        "no-dupe-args": 2, // Disallows duplicate arguments in function definitions
        "no-dupe-class-members": 2, // Disallows duplicate class members
        "no-dupe-keys": 2, // Disallows duplicate keys in object literals
        "no-duplicate-case": 2, // Disallows duplicate case labels
        "no-empty-character-class": 2, // Disallows empty character classes in regular expressions
        "no-empty-pattern": 2, // Disallows empty destructuring patterns
        "no-eval": 2, // Disallows eval()
        "no-ex-assign": 2, // Disallows reassigning exceptions in catch clauses
        "no-extend-native": 2, // Disallows extending native types
        "no-extra-bind": 2, // Disallows unnecessary calls to .bind()
        "no-extra-boolean-cast": 2, // Disallows unnecessary boolean casts
        "no-extra-parens": [2, "functions"], // Disallows unnecessary parentheses
        "no-fallthrough": 2, // Disallows fallthrough of case statements
        "no-floating-decimal": 2, // Disallows leading or trailing decimal points in numeric literals
        "no-func-assign": 2, // Disallows reassigning function declarations
        "no-implied-eval": 2,  // Disallows the use of eval()-like methods
        "no-inner-declarations": [2, "functions"], // Disallows function or variable declarations in nested blocks
        "no-invalid-regexp": 2, // Disallows invalid regular expression strings in RegExp constructors
        "no-irregular-whitespace": 2, // Disallows irregular whitespace outside of strings and comments
        "no-iterator": 2, // Disallows the use of the __iterator__ property
        "no-label-var": 2, // Disallows labels that share a name with a variable
        "no-labels": [2, { // Disallows labeled statements
          "allowLoop": false,
          "allowSwitch": false
        }],
        "no-lone-blocks": 2, // Disallows unnecessary nested blocks
        "no-mixed-spaces-and-tabs": 2, // Disallows mixed spaces and tabs for indentation
        "no-multi-spaces": 2, // Disallows multiple spaces
        "no-multi-str": 2, // Disallows multiline strings
        "no-multiple-empty-lines": [1, { // Disallows multiple empty lines
          "max": 2
        }],
        "no-native-reassign": 2, // Disallows reassigning native objects
        "no-negated-in-lhs": 2, // Disallows negating the left operand in in expressions
        "no-new-object": 2, // Disallows Object constructors
        "no-new-require": 2, // Disallows new require
        "no-new-symbol": 2, // Disallows new Symbol
        "no-new-wrappers": 2, // Disallows new String, Number, and Boolean
        "no-obj-calls": 2, // Disallows calling global object properties as functions
        "no-octal": 2, // Disallows octal literals
        "no-octal-escape": 2, // Disallows octal escape sequences in string literals
        "no-path-concat": 2, // Disallows __dirname and __filename concatenation
        "no-proto": 2, // Disallows the use of the __proto__ property
        "no-redeclare": 2, // Disallows reassigning const variables
        "no-regex-spaces": 2, // Disallows multiple spaces in regular expression literals
        "no-return-assign": [2, "except-parens"], // Disallows assignment operators in return statements
        "no-self-assign": 2, // Disallows self-assignment
        "no-self-compare": 2, // Disallows self-compare
        "no-sequences": 2, // Disallows comma operators
        "no-shadow-restricted-names": 2, // Disallows shadowing restricted names
        "no-spaced-func": 2, // Disallows spacing between function identifiers and their applications
        "no-sparse-arrays": 2, // Disallows sparse arrays
        "no-this-before-super": 2, // Disallows this/super before calling super() in constructors
        "no-throw-literal": 2, // Disallows throwing literals as exceptions
        "no-trailing-spaces": 0, // Disallows trailing whitespace at the end of lines
        "no-undef": 2, // Disallows undeclared variables
        "no-undef-init": 2, // Disallows initializing variables to undefined
        "no-unexpected-multiline": 2, // Disallows confusing multiline expressions
        "no-unmodified-loop-condition": 2, // Disallows unmodified loop conditions
        "no-unneeded-ternary": [2, { // Disallows ternary operators when simpler alternatives exist
          "defaultAssignment": false // Disallows the conditional expression as the default assignment pattern
        }],
        "no-unreachable": 2, // Disallows unreachable code after return, throw, continue, and break statements
        "no-unsafe-finally": 2, // Disallows control flow statements in finally blocks
        "no-unused-vars": [2, { // Disallows unused variables
          "vars": "all",
          "args": "none"
        }],
        "no-useless-call": 2, // Disallows unnecessary calls to .call() and .apply()
        "no-useless-computed-key": 2, // Disallows unnecessary computed property keys in object literals
        "no-useless-constructor": 2, // Disallows unnecessary constructors
        "no-useless-escape": 0, // Disallows unnecessary escape characters
        "no-whitespace-before-property": 0, // Disallows whitespace before properties
        "no-with": 2, // Disallows with statements
        "one-var": [2, "never"], // Enforces variables to be declared either together or separately in functions
        "operator-linebreak": [2, "after", { // Enforces operators to be placed before or after line breaks
          "overrides": { // Overrides the default behavior for specified operators
            "?": "before",
            ":": "before"
          }
        }],
        "padded-blocks": [0, "never"], // Enforces blank lines inside of blocks
        "quotes": [2, "double", {  // Enforces the consistent use of either backticks, double, or single quotes
          "avoidEscape": true,
          "allowTemplateLiterals": true
        }],
        "semi": [0, "never"], // Enforces semicolons after every statement
        "semi-spacing": [0, { // Enforces spacing before and after semicolons
          "before": false,
          "after": true
        }],
        "space-before-blocks": [2, "always"], // Enforces spacing before blocks
        "space-before-function-paren": [0, "never"], // Enforces spacing before function parenthesis
        "space-in-parens": [2, "never"], // Enforces spacing inside of parentheses
        "space-infix-ops": 2, // Enforces spacing around infix operators
        "space-unary-ops": [2, { // Enforces spacing around unary operators
          "words": true,
          "nonwords": false
        }],
        "spaced-comment": [2, "always", { // Enforces spacing after the // or /* in a comment
          "markers": ["global", "globals", "eslint", "eslint-disable", "*package", "!", ","]
        }],
        "template-curly-spacing": [0, "never"], // Enforces spacing around embedded expressions of template strings
        "use-isnan": 2, // Enforces the use of isNaN()
        "valid-typeof": 2, // Enforces comparing typeof expressions against valid strings
        "wrap-iife": [2, "any"], // Enforces parentheses around IIFEs
        "yield-star-spacing": [2, "both"], // Enforces spacing around the * in yield* expressions
        "yoda": [2, "never"], // Enforces "Yoda" conditions
        "prefer-const": 2, // Prefer const over let
        "object-curly-spacing": [0, "always", { // Enforces spacing inside of braces
          "objectsInObjects": false
        }],
        "array-bracket-spacing": [0, "never"], // Enforces spacing inside of brackets
        "linebreak-style": 0, // Enforces a consistent linebreak style
        "no-var": 2, // Disallows the use of var
        "no-extra-semi": 0, // Disallows unnecessary semicolons
        "no-unsafe-negation": 2, // Disallows negating the left operand of relational operators
        "curly": 2, // Enforces consistent brace style for all control statements
        "eqeqeq": 2, // Enforces the use of === and !==
        "no-else-return": 2, // Disallows unnecessary else blocks
        "no-unused-expressions": [2, { // Disallows unused expressions
          "allowShortCircuit": true,
          "allowTernary": true
        }],
        "no-useless-return": 2, // Disallows unnecessary return await
        "consistent-this": 0, // Enforces consistent naming when capturing the current execution context
        "function-paren-newline": [2, "multiline"], // Enforces consistent line breaks inside parentheses of function parameters
        "implicit-arrow-linebreak": [2, "beside"], // Enforces consistent line breaks before and after the arrow in arrow functions
        "indent": [2, 2, { // Enforces a consistent indentation style
          "SwitchCase": 1
        }],
        "lines-between-class-members": 2,  // Enforces empty lines between class members
        "max-depth": 2, // Enforces a maximum depth that blocks can be nested
        "no-inline-comments": 2, // Disallows comments inline after code
        "no-mixed-operators": [2, { // Disallows mixed binary operators
          "groups": [
            ["*", "/", "%", "**"],
            ["&", "|", "^", "~", "<<", ">>", ">>>"],
            ["==", "!=", "===", "!==", ">", ">=", "<", "<="],
            ["&&", "||"],
            ["in", "instanceof"]
          ],
          "allowSamePrecedence": true
        }],
        "padding-line-between-statements": [  // Requires or disallows padding lines between statements
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
