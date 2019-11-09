<!-- React project with webpack and typescript --> 

run application with below command.
---

```bash
npm start
```
*this will start the at localhost:8080*

bundle resource using webpack 
---

```bash
sudo npm run-script bundle
```
*static resource will be available inside dist folder of project root directory*

git
---

```bash
echo "# react-typescript-webpack" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github.com:Ranjit-Banglore/react-typescript-webpack.git
git push -u origin master
```

.gitignore
---

```code
.idea
dist
node_modules
*.yarn
*.iml
```
/.babelrc
--
```code
{
    "presets": [
        "@babel/preset-env",
        "@babel/preset-typescript",
        "@babel/preset-react"
    ],
    "plugins": [
        "@babel/proposal-class-properties",
        "@babel/proposal-object-rest-spread"
    ]
}

```

/typings/override.d.ts
--
```code
declare module package-with-no-typings-file
```

/package.json
--
```javascript
{
  "name": "react-typescript-boilerplate",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "bundle": "webpack",
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "webpack-dev-server --mode development --open --hot",
    "build": "webpack --mode production",
    "check-types": "tsc"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "@babel/core": "^7.7.2",
    "@babel/plugin-proposal-class-properties": "^7.7.0",
    "@babel/plugin-proposal-object-rest-spread": "^7.6.2",
    "@babel/preset-env": "^7.7.1",
    "@babel/preset-react": "^7.7.0",
    "@babel/preset-typescript": "^7.7.2",
    "babel-loader": "^8.0.6",
    "css-loader": "^3.2.0",
    "html-webpack-plugin": "^3.2.0",
    "style-loader": "^1.0.0",
    "tslint": "^5.20.1",
    "tslint-immutable": "^6.0.1",
    "typescript": "^3.7.2",
    "webpack": "^4.41.2",
    "webpack-cli": "^3.3.10",
    "webpack-dev-server": "^3.9.0"
  },
  "dependencies": {
    "@types/react": "^16.9.11",
    "@types/react-dom": "^16.9.4",
    "react": "^16.11.0",
    "react-dom": "^16.11.0"
  }
}

```

/tsconfig.json
--
```javascript
{
	"compilerOptions": {
		// Target latest version of ECMAScript.
		"target": "esnext",
		// path to output directory
		"outDir": "./dist/",
		// enable strict null checks as a best practice
		"strictNullChecks": true,
		// Search under node_modules for non-relative imports.
		"moduleResolution": "node",
		// Process & infer types from .js files.
		"allowJs": true,
		// Don't emit; allow Babel to transform files.
		"noEmit": true,
		// Enable strictest settings like strictNullChecks & noImplicitAny.
		"strict": true,
		// Import non-ES modules as default imports.
		"esModuleInterop": true,
		// use typescript to transpile jsx to js
		"jsx": "react",
		"baseUrl": "./src",
		"lib": [
			"es2015",
			"dom.iterable",
			"es2016.array.include",
			"es2017.object",
			"dom"
		],
		"module": "es6",
		"removeComments": true,
		"alwaysStrict": true,
		"allowUnreachableCode": false,
		"noImplicitAny": true,
		"noImplicitThis": true,
		"noUnusedLocals": true,
		"noUnusedParameters": true,
		"noImplicitReturns": true,
		"noFallthroughCasesInSwitch": true,
		"forceConsistentCasingInFileNames": true,
		"importHelpers": true
	},
}

```

/tslint.json
--
```javascript
{
	"extends": [
		"tslint-immutable"
	],
	"rules": {
		"no-var-keyword": true,
		"no-parameter-reassignment": true,
		"typedef": false,
		"readonly-keyword": false,
		"readonly-array": false,
		"no-let": false,
		"no-array-mutation": true,
		"no-object-mutation": false,
		"no-this": false,
		"no-class": false,
		"no-mixed-interface": false,
		"no-expression-statement": false,
		"member-ordering": [
			true,
			"variables-before-functions"
		],
		"no-any": false,
		"no-inferrable-types": [
			false
		],
		"no-internal-module": true,
		"no-var-requires": false,
		"typedef-whitespace": [
			true,
			{
				"call-signature": "nospace",
				"index-signature": "nospace",
				"parameter": "nospace",
				"property-declaration": "nospace",
				"variable-declaration": "nospace"
			},
			{
				"call-signature": "space",
				"index-signature": "space",
				"parameter": "space",
				"property-declaration": "space",
				"variable-declaration": "space"
			}
		],
		"ban": false,
		"curly": false,
		"forin": true,
		"label-position": true,
		"no-arg": true,
		"no-bitwise": false,
		"no-conditional-assignment": true,
		"no-console": [
			true,
			"info",
			"time",
			"timeEnd",
			"trace"
		],
		"no-construct": true,
		"no-debugger": true,
		"no-duplicate-variable": true,
		"no-empty": false,
		"no-eval": true,
		"strictPropertyInitialization": false,
		"no-null-keyword": false,
		"no-shadowed-variable": false,
		"no-string-literal": false,
		"no-switch-case-fall-through": true,
		"no-unused-expression": [
			true,
			"allow-fast-null-checks"
		],
		"no-use-before-declare": true,
		"radix": true,
		"switch-default": true,
		"triple-equals": [
			true,
			"allow-undefined-check",
			"allow-null-check"
		],
		"eofline": false,
		"indent": [
			true,
			"tabs"
		],
		"max-line-length": [
			true,
			250
		],
		"no-require-imports": false,
		"no-trailing-whitespace": true,
		"object-literal-sort-keys": false,
		"trailing-comma": [
			true,
			{
				"multiline": "never",
				"singleline": "never"
			}
		],
		"align": [
			true
		],
		"class-name": true,
		"comment-format": [
			true,
			"check-space"
		],
		"interface-name": [
			false
		],
		"jsdoc-format": true,
		"no-consecutive-blank-lines": [
			true
		],
		"no-parameter-properties": false,
		"one-line": [
			true,
			"check-open-brace",
			"check-catch",
			"check-else",
			"check-finally",
			"check-whitespace"
		],
		"quotemark": [
			true,
			"single",
			"avoid-escape"
		],
		"semicolon": [
			true,
			"always"
		],
		"variable-name": [
			false,
			"check-format",
			"allow-leading-underscore",
			"ban-keywords"
		],
		"whitespace": [
			true,
			"check-branch",
			"check-decl",
			"check-operator",
			"check-separator",
			"check-type"
		]
	}
}

```

/webpack.config.js
---
```javascript
const path = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');
module.exports = {

  // webpack will take the files from ./src/index
  entry: './src/index',

  // and output it into /dist as bundle.js
  output: {
    path: path.join(__dirname, '/dist'),
    filename: 'index.html'
  },

  // adding .ts and .tsx to resolve.extensions will help babel look for .ts and .tsx files to transpile
  resolve: {
    extensions: ['.ts', '.tsx', '.js']
  },

  module: {
    rules: [

        // we use babel-loader to load our jsx and tsx files
      {
        test: /\.(ts|js)x?$/,
        exclude: /node_modules/,
        use: {
          loader: 'babel-loader'
        },
      },

      // css-loader to bundle all the css files into one file and style-loader to add all the styles  inside the style tag of the document
      {
        test: /\.css$/,
        use: ['style-loader', 'css-loader']
      }
    ]
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: './src/index.html'
    })
  ]
};

```