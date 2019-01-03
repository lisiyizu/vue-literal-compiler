# Vue Literal Compiler
A simple stand in replacement for the default vue-template-compiler that allows you write Vue Templates, Scoped CSS, Custom Blocks and Scripts in SFC format all in your JavaScript/TypeScript files.

## Motivation
* Maintain the SFC paradigm. Write all your Templates, Styles and Scripts in one file (JavaScript/TypeScript)
* Compiles your literal templates into render functions at compile time rather than at runtime.
* Provide Support for CSS in JavaScript/TypeScript.
* Provide Support for Scoped CSS
* Provide support for SASS, SCSS, LESS etc. using the lang attribute.
* Provide Support for Custom Blocks in JavaScript/TypeScript.
* Provide Support for lintable typesafe templates using Functional Templates

## Who This Library is For
If you're like me and you love developing in TypeScript and you want to get the best TypeScript experience from Vue, then this library is for you.

## Example
Below is a normal .vue Single File Component.\
\
![alt text](./images/1-1.png)

This same component using in a TypeScript File with Vue Literal Compiler would look like this.\
\
![alt text](./images/2-1.png)\
\
Syntax highligting in string literals is achieved with a vscode extension lit-html.


## TypeSafe Functional Templates
Inspired by Polymer, functional templates give you the ability to write typesafe templates.\
Example:
![alt text](./images/3-1.png)

Now you can easily auto refractor name and sayHi.

## How To Use

Install Vue Literal Compiler
```
  npm install --save-dev vue-literal-compiler
```
\
Include it in your webpack.config.js vue-loader options.\
\
![alt text](./images/4-1.png)\
\
Add an additional Vue Loader Configuration. 
This is to appease VueLoaderPlugin and prevent it from squawking. 

See issue https://github.com/vuejs/vue-loader/issues/1238 \
\
![alt text](./images/4-2.png) \
\
Finally since we're using plain TypeScript / JavaScript files rather than .vue files, We have to stop ts-loader or babel from attempting to parse our .vue.ts or .vue.js files. We do this by telling webpack to exclude those files.\
So in ts-loader config\
\
![alt text](./images/4-3.png)

## Custom Blocks
Vue also give you the ability to define Custom Blocks in your .vue files. To use custom blocks with Vue Literal Compiler, we simply do the following:\
\
![alt text](./images/5-1.png)

## Multiple Styles
Just like in your .vue files where you can include multiple style tags, it is possible in .vue.ts files like so: \
\
![alt text](./images/6-1.png)
