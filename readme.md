# calcUTDelay

[![GitHub license](https://img.shields.io/badge/license-MIT-brightgreen.svg)](#) [![npm version](https://img.shields.io/npm/v/react.svg?style=flat)](https://www.npmjs.com/package/@behaver/calc-ut-delay) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](#)

## 简介

计算 **力学时** 与 **世界时** 之差，即 *ΔT = TD - UT*，单位为 **秒**

**世界时（UT）**，即格林威治地方时，它 *基于地球的自转*。
然而，地球自转一直在变缓，而且变缓规律难以预测，这使得世界时成了一种不均匀的时间系统。

**历书时（ET）**，它由力学定律定义：*基于行星运动*。
1984年，ET被 **力学时** 取代，它由 *原子钟定义*。事实上，力学时是历书时的一个延伸。
它是一个均匀的时间标尺，被天文学家们用来精确计算天体力学、轨道和星历等。

力学时又分为太阳系 **质心力学时（TDB）** 和 **地心力学时（TDT）** 。
这两个系统最多相差0.0017秒，此种差异与地球以椭圆轨道绕日运动有关(相对论效应)。
因这一差异小到可以被大多数实际应用忽略，故此处我们对质心力学时和地球力学时不加区分，统称为**力学时（TD）**。

本函数求得的数值为 近似 差值，力学时和世界时之间的 精确 差值 *ΔT = TD - UT* 只能由天文观测值推算。

除了 1871 - 1901 年，世界时总是落后于相同数值的力学时，所以该段时间之外的年份，函数的结果都是正值。

本函数计算值域在 *-4000年 至 6000年* 之间。

*本函数参考了 许剑伟 先生的寿星万年历程序，特此申明。*

## 用例

通过 npm 安装，在你的 node 项目目录下执行：

`npm install @behaver/calc-ut-delay`

---

计算 1100 年的力学时与世界时之差 ΔT：

```js
const calcUTDelay = require('@behaver/calc-ut-delay');
let deltaT = calcUTDelay(1100).toFixed(1);
```

变量 deltaT 的值等于 `1089.8` 秒

## 误差分析

通过本方法计算得到的 ΔT 存在一定计算误差，精确 ΔT 只能由天文观测值推算

从 1800年 至今 函数的平均计算误差保持在 1 秒之内

对于早于 1800年 的时间，随着年代越早，误差不断增大

至 -500年 时，误差可达到 430 秒左右

关于计算误差的详细情况，可参照 http://www.huangdaojiri.org/wnl/sm7.htm

或 NASA 提供的 https://eclipse.gsfc.nasa.gov/SEcat5/deltat.html

## 贡献者

本函数参考了 许剑伟 先生的寿星万年历程序，特此申明。

## 许可证书

The MIT license.
