---
title: Custom Plots
order: 6
---

## Custom chart development

G2Plot has built-in regular statistical charts that account for more than 90% of the business usage. However, customization is inevitable for business products. At this time, users will face a dilemma:

 - Use G2
 - Suggest G2Plot to add charts
 - Use other products or develope their own charts

As G2Plot developers, we also get into some problems:

1. Is this chart universal? Are we following the business too much? Can it be built in directly?
2. Can the chart developed based on G2, be opened to other users?

Based on these problems, we directly open the adapter mode of G2Plot based on G2 chart. You can package customized charts based on this G2 pattern. If you need to reuse, you can directly produce NPM packages and use them in the G2Plot mode. Take a simple example:

```ts
// entrance of importing custom chart
import { P } from '@antv/g2plot';
// import your own chart(QR code)
import { adaptor, defaultOptions } from 'g2plot-qrcode';

const plot = new P('container', {
  data: 'Hello, G2Plot v2!', // content of QR code
}, adaptor, defaultOptions);

plot.render();
```

In such an open and extended development mode, it can not only ensure the unification of business technology stack, but also ensure that the built-in charts of G2Plot are universal, and make full use of G2.


## How to develop custom chart

This section describes how to develop a custom chart. Example:

<playground path="plugin/basic/demo/hill-column.ts"></playground>

The main process is divided into the following steps:

1. Define chart default configuration
2. Custom adaptor to realize the transformation from configuration to G2 API
3. Use it on G2Plot, or publish NPM package


## Customized third-party charts

> Based on the `open development capability` of G2Plot, customized third-party charts make up for the limitation of G2Plot official general chart collection standard and quantity. Packages come from the community, so please choose carefully for production environment.

| Project name | Demonstration | Description | Version |
|---|---|---|---|
| [G2Plot-QRCode](https://github.com/hustcc/G2Plot-QRCode) | [Go](https://git.hust.cc/G2Plot-QRCode) | Draw a QRCode with G2Plot. | [![npm](https://img.shields.io/npm/v/g2plot-qrcode.svg)](https://www.npmjs.com/package/g2plot-qrcode) |
| [G2Plot-Column](https://github.com/yujs/G2Plot-Column) | [Go](https://yujs.github.io/G2Plot-Column/) | Customize Column with G2Plot. | [![npm](https://img.shields.io/npm/v/g2plot-column.svg)](https://www.npmjs.com/package/g2plot-column) | 


## Technology stack packages

> Technology stack packages ( React、Vue、Angular ) come from the community, so please choose carefully for production environment.

| Project name | Technology stack | Description | Version |
|---|---|---|---|
| [@ant-design/charts](https://github.com/ant-design/ant-design-charts) | **React** | A React Chart Library based on `@antvis/G2Plot`. | ![npm](https://img.shields.io/npm/v/@ant-design/charts) |
| [React-G2Plot](https://github.com/hustcc/React-G2Plot) | **React** | Unofficial react component wrapper for `@antvis/G2Plot`. | ![npm](https://img.shields.io/npm/v/react-g2plot.svg) |
| [@opd/g2plot-react](https://github.com/open-data-plan/g2plot-react) | **React** | G2Plot for React. | ![npm](https://img.shields.io/npm/v/@opd/g2plot-react.svg) |
| [@opd/g2plot-vue](https://github.com/open-data-plan/g2plot-vue) | **Vue** | G2Plot for Vue 3. | ![npm](https://img.shields.io/npm/v/@opd/g2plot-vue.svg) |