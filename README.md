# canvas-barrage

[![Build Status](https://travis-ci.org/zhaofinger/canvas-barrage.svg?branch=master)](https://travis-ci.org/zhaofinger/canvas-barrage)

一个基于canvas的弹幕发射器，查看[线上demo](https://zhaofinger.github.io/canvas-barrage/index.html)

## Build

- installation dependence
    ```bash
    yarn // or npm install
    ```

- build for es5
    ```bash
    gulp build_es5
    ```

- build for es6
    ```bash
    gulp build_es6
    ```

## Usage

- used in es5
    ```html
    <canvas width='700' height='400'></canvas>
    <script src="../dist/index.js"></script>
    <script>
        let canvasEle = document.querySelector('canvas')
        let barrage = new Barrage(canvasEle)
        barrage.pushMessage({text: '弹幕发射，biu'})
    </script>
    ```
- used in es6
    1. install package
        ```bash
        yarn add canvas-barrage // or npm install canvas-barrage
        ````
    1. use
        ```html
        <canvas width='700' height='400'></canvas>
        <script>
            import Barrage from 'canvas-barrage'
            let canvasEle = document.querySelector('canvas')
            let barrage = new Barrage(canvasEle)
            barrage.pushMessage({text: '弹幕发射，biu'})
        </script>
        ```

## Apis

- `new Barrage(options)` - 构造函数，初始化

    | # | name | type | default | desc |
    | :--- | :--- |:--- | :--- | :--- |
    | 1 | `canvasDom` | `object` | `null` | 必填，`canvas` dom对象 |
    | 2 | `msgStackLength` | `number` | `300` | 最多弹幕数 |
    | 3 | `fontSize` | `number` | `10` | 字体大小 |

- `.pushMessage(options)` - 发送弹幕

    | # | name | type | default | desc |
    | :--- | :--- |:--- | :--- | :--- |
    | 1 | `text` | `string` | '' | 必填，弹幕文字内容 |
    | 2 | `color` | `string` | 随机色 | 弹幕颜色，非指定的情况下随机取色 |
    | 3 | `speed` | `number` | 2到4的随机色 | 弹幕移动速度 |

- `.clear()` - 清除

- `.close()` - 关闭弹幕

- `.open()` - 开启弹幕