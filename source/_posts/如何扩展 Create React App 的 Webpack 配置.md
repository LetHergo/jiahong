---
title: 如何扩展 Create React App 的 Webpack 配置
date: 2018-5-0
categories:
  - javascript
  - react
tags:
  - javascript
  - react
---

# 如何扩展 Create React App 的 Webpack 配置

Create React App（以下简称 CRA）是创建 React 应用的一个脚手架，它与其他脚手架不同的一个地方就是将一些复杂工具（比如 webpack）的配置封装了起来，让使用者不用关心这些工具的具体配置，从而降低了工具的使用难度。

但是对于一些熟悉 webpack 的开发者来说，他们可能想对 webpack 配置做一些修改，这个时候应该怎么办呢？
其实我们可以通过以下几种方式来修改 webpack 的配置：

- 项目 eject
- 替换 react-scripts 包
- 使用 react-app-rewired
- scripts 包 + override 组合

## 项目 eject

使用 CRA 创建完项目以后，项目在 package.json 里面提供了这样一个命令：

```
{
  ...
  "scripts": {
    "eject": "react-scripts eject"
  },
  ...
}
```
