# native-echarts

[![NPM Version](https://img.shields.io/npm/v/native-echarts.svg?style=flat)](https://www.npmjs.org/package/native-echarts)
  [![npm](https://img.shields.io/npm/dm/native-echarts.svg?style=flat)](https://www.npmjs.org/package/native-echarts)
  [![License](http://img.shields.io/npm/l/native-echarts.svg?style=flat)](https://raw.githubusercontent.com/somonus/react-native-echarts/master/LICENSE.md)
  
## install

$ npm install @iwubida/native-echarts --save

## Android 打包

在项目根目录文件夹下使用命令：

打包 Android 需要先把 tpl.html（路径： node_modules\native-echarts\src\components\Echarts）拷贝到 android\app\src\main\assets目录下

## Usage

The Usage is complete consistent with Echarts

component props:

* *option* (object): The option for echarts: [Documentation](http://echarts.baidu.com/option.html#title)。 
* *width* (number): The width of the chart. The default value is the outer container width. 
* *height* (number): The height of the chart. The default value is 400. 


```js
import React, { Component } from 'react';
import {
  AppRegistry,
  StyleSheet,
  Text,
  View
} from 'react-native';
import Echarts from '@iwubida/native-echarts';

export default class app extends Component {
  render() {
    const option = {
      xAxis: {
        name: `入店人数趋势图`,
        nameTextStyle: {
          color: '#121212',
          fontSize: 13
        },
        nameLocation: 'middle',
        nameGap: 40,
        type: 'category',
        boundaryGap: false,
        data: ['01/03', '01/04', '01/05', '01/06', '01/07', '01/08', '01/09'],
        splitLine: {
          lineStyle: {
            color: '#f8f8f8'
          },
          show: true
        },
        axisLabel: {
          show: true,
          textStyle: {
            color: '#999'
          }
        },
        axisLine: {
          lineStyle: {
            color: '#e5e5e5'
          }
        }
      },
      yAxis: {
        type: 'value',
        splitLine: {
          lineStyle: {
            color: '#f8f8f8'
          },
          show: true
        },
        axisLabel: {
          show: true,
          textStyle: {
            color: '#999'
          }
        },
        axisLine: {
          lineStyle: {
            color: '#f8f8f8'
          }
        }
      },
      series: [
        {
          data: [200, 500, 300, 400, 599, 200, 100],
          type: 'line',
          itemStyle: {
            normal: {
              color: '#0BA5F0',
              lineStyle: {
                color: '#0BA5F0',
                opacity: 0.8
              }
            }
          },
          areaStyle: {
            normal: {
              color: 'rgba(11, 165, 240, .1)'
            }
          }
        }
      ]
    }
    return (
      <Echarts option={option} height={300} />
    );
  }
}

AppRegistry.registerComponent('app', () => app);

```



##Example

*run demo*

```
cd example
npm install
npm start
```

### IOS

Open the xcode project in the ios directory and click run

screenshots：

![image](https://github.com/iwubida/react-native-echarts/blob/master/example/demoIOS.jpg)

### Android

Open the Android project in the android directory with Android Studio and click run.

screenshots：

![image](https://github.com/iwubida/react-native-echarts/blob/master/example/demoAndroid.jpg)

## License

native-echarts is released under the MIT license.
