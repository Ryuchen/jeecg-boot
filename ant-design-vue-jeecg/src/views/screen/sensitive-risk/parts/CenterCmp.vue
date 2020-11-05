<template>
  <div class="center-cmp">
    <div class="cc-top" >
      <dv-charts :option="option1" />
      <dv-charts :option="option2" />
    </div>
    <div class="cc-button">
      <dv-charts :option="option3" />
      <dv-charts :option="option4" />
    </div>


  </div>
</template>


<script>
  import { changeDefaultConfig } from '@jiaminghi/charts'

  //changeDefaultConfig('color', ['#fff'])
 // @description 图表全局配色
  //@type {Array}
  //@default color = []

  export default {

    name: 'CenterCmp',
    data () {
      return {

        option1: {
          grid:{           //坐标系大小
            top:45,
            bottom:35,

          },
          title: {
            text: '大豆价格波动趋势',
            style: {
              fill: '#ffffff',
              fontSize: 17,
              fontWeight: 'bold',
              textAlign: 'center',
              textBaseline: 'bottom'
            }
          },
          xAxis: {
            name: '2019年',
            nameGap:10,
            nameTextStyle: {
              fill: '#ffffff',
              fontSize: 10,

            },
            data: ['一月', '二月', '三月', '四月', '五月', '六月', '七月','八月', '九月', '十月', '十一月', '十二月'],
            dataByText:
              {
                fill: '#ffffff',
                fontSize: 10
              },
            axisLine: //坐标轴线配置
              {
              style: {
                stroke: '#ffffff',
                lineWidth: 1
              }
              },
            axisTick://坐标刻度配置
              {
                style: {
                  stroke: '#ffffff',
                  lineWidth: 1
                }
              },
            axisLabel://坐标轴标签配置
              {
                style: {
                  fill: '#ffffff',
                  fontSize: 10,
                }
              }
          },
          yAxis: {
            name: '价格/元/斤',
            nameGap:10,
            nameTextStyle: {
              fill: '#ffffff',
              fontSize: 10,

            },
            data: 'value',
            min:1, //坐标轴最小值
            max:3,//坐标轴最大值
            interval:0.5,//坐标轴数值间隔
            dataByText:
              {
                fill: '#ffffff',
                fontSize: 10
              },
            axisLine: //坐标轴线配置
              {
                style: {
                  stroke: '#ffffff',
                  lineWidth: 1
                }
              },
            axisTick://坐标刻度配置
              {
                style: {
                  stroke: '#ffffff',
                  lineWidth: 1
                }
              },
            axisLabel://坐标轴标签配置
              {
                style: {
                  fill: '#ffffff',
                  fontSize: 10,
                }
              }

          },
          series: [
            {
              data: [1.75, 1.83, 1.78, 1.93, 1.86, 1.90, 1.88,2.02, 2.00, 1.96, 1.88, 1.91],
              type: 'line',
              lineArea: {
                show: true
              }
            }
          ]
        },

        option2: {
          grid:{           //坐标系大小
            top:45,
            bottom:35,

          },
          title: {
            text: '大豆交易量波动趋势',
            style: {
              fill: '#ffffff',
              fontSize: 17,
              fontWeight: 'bold',
              textAlign: 'center',
              textBaseline: 'bottom'
            }
          },
          xAxis: {
            name: '2019年',
            nameGap:10,
            nameTextStyle: {
              fill: '#ffffff',
              fontSize: 10,

            },
            data: ['一月', '二月', '三月', '四月', '五月', '六月', '七月','八月', '九月', '十月', '十一月', '十二月'],
            dataByText:
              {
                fill: '#ffffff',
                fontSize: 10
              },
            axisLine: //坐标轴线配置
              {
                style: {
                  stroke: '#ffffff',
                  lineWidth: 1
                }
              },
            axisTick://坐标刻度配置
              {
                style: {
                  stroke: '#ffffff',
                  lineWidth: 1
                }
              },
            axisLabel://坐标轴标签配置
              {
                style: {
                  fill: '#ffffff',
                  fontSize: 10,
                }
              }
          },
          yAxis: {
            name: '重量/万吨',
            nameGap:10,
            nameTextStyle: {
              fill: '#ffffff',
              fontSize: 10,

            },
            data: 'value',
            min:500, //坐标轴最小值
            max:1500,//坐标轴最大值
            interval:100,//坐标轴数值间隔
            dataByText:
              {
                fill: '#ffffff',
                fontSize: 10
              },
            axisLine: //坐标轴线配置
              {
                style: {
                  stroke: '#ffffff',
                  lineWidth: 1
                }
              },
            axisTick://坐标刻度配置
              {
                style: {
                  stroke: '#ffffff',
                  lineWidth: 1
                }
              },
            axisLabel://坐标轴标签配置
              {
                style: {
                  fill: '#ffffff',
                  fontSize: 10,
                }
              }

          },
          series: [
            {
              data: [750, 830, 790, 820, 850, 930, 970,880, 810, 790, 880, 920],
              type: 'line',
              lineArea: {
                show: true
              }
            }
          ]
        },

        option3: {
            grid:{           //坐标系大小
              top:40,
              bottom:42,

            },
            title: {
              text: '大豆交易额波动趋势',
              style: {
                fill: '#ffffff',
                fontSize: 17,
                fontWeight: 'bold',
                textAlign: 'center',
                textBaseline: 'bottom'
              }
            },
            xAxis: {
              name: '2019年',
              nameGap:10,
              nameTextStyle: {
                fill: '#ffffff',
                fontSize: 10,

              },
              data: ['一月', '二月', '三月', '四月', '五月', '六月', '七月','八月', '九月', '十月', '十一月', '十二月'],
              dataByText:
                {
                  fill: '#ffffff',
                  fontSize: 10
                },
              axisLine: //坐标轴线配置
                {
                  style: {
                    stroke: '#ffffff',
                    lineWidth: 1
                  }
                },
              axisTick://坐标刻度配置
                {
                  style: {
                    stroke: '#ffffff',
                    lineWidth: 1
                  }
                },
              axisLabel://坐标轴标签配置
                {
                  style: {
                    fill: '#ffffff',
                    fontSize: 10,
                  }
                }
            },
            yAxis: {
              name: '交易额/亿元',
              nameGap:10,
              nameTextStyle: {
                fill: '#ffffff',
                fontSize: 10,

              },
              data: 'value',
              min:100, //坐标轴最小值
              max:500,//坐标轴最大值
              interval:100,//坐标轴数值间隔
              dataByText:
                {
                  fill: '#ffffff',
                  fontSize: 10
                },
              axisLine: //坐标轴线配置
                {
                  style: {
                    stroke: '#ffffff',
                    lineWidth: 1
                  }
                },
              axisTick://坐标刻度配置
                {
                  style: {
                    stroke: '#ffffff',
                    lineWidth: 1
                  }
                },
              axisLabel://坐标轴标签配置
                {
                  style: {
                    fill: '#ffffff',
                    fontSize: 10,
                  }
                }

            },
            series: [
              {
                data: [240, 200, 260, 300, 450, 330, 290,190, 440, 300, 220, 250],
                type: 'line',
                lineArea: {
                  show: true
                }
              }
            ]
          },

        option4: {
          grid:{           //坐标系大小
            top:40,
            bottom:42,

          },
          title: {
            text: '大豆进口数量波动趋势',
            style: {
              fill: '#ffffff',
              fontSize: 17,
              fontWeight: 'bold',
              textAlign: 'center',
              textBaseline: 'bottom'
            }
          },
          xAxis: {
            name: '2019年',
            nameGap:10,
            nameTextStyle: {
              fill: '#ffffff',
              fontSize: 10,

            },
            data: ['一月', '二月', '三月', '四月', '五月', '六月', '七月','八月', '九月', '十月', '十一月', '十二月'],
            dataByText:
              {
                fill: '#ffffff',
                fontSize: 10
              },
            axisLine: //坐标轴线配置
              {
                style: {
                  stroke: '#ffffff',
                  lineWidth: 1
                }
              },
            axisTick://坐标刻度配置
              {
                style: {
                  stroke: '#ffffff',
                  lineWidth: 1
                }
              },
            axisLabel://坐标轴标签配置
              {
                style: {
                  fill: '#ffffff',
                  fontSize: 10,
                }
              }
          },
          yAxis: {
            name: '数量/万吨',
            nameGap:10,
            nameTextStyle: {
              fill: '#ffffff',
              fontSize: 10,

            },
            data: 'value',
            min:500, //坐标轴最小值
            max:1300,//坐标轴最大值
            interval:100,//坐标轴数值间隔
            dataByText:
              {
                fill: '#ffffff',
                fontSize: 10
              },
            axisLine: //坐标轴线配置
              {
                style: {
                  stroke: '#ffffff',
                  lineWidth: 1
                }
              },
            axisTick://坐标刻度配置
              {
                style: {
                  stroke: '#ffffff',
                  lineWidth: 1
                }
              },
            axisLabel://坐标轴标签配置
              {
                style: {
                  fill: '#ffffff',
                  fontSize: 10,
                }
              }

          },
          series: [
            {
              data: [660, 690, 730, 820, 770, 790, 895,900, 770, 710, 920, 880],
              type: 'line',
              lineArea: {
                show: true
              }
            }
          ]
        }
      }
    }
  }


</script>

<style lang="less">
.center-cmp {
  width: 100%;
  height: 100%;
  margin: 0px;
  padding: 0px;
  display: flex;
  flex-direction: column;

  /*background-image: url('./bg.png');
  background-size: 100% 100%;
  background-position-y:10px;
  filter:opacity(65%);*/


  .cc-top {
    //stroke: #990000;
    height: 50%;
    display: flex;
    font-size: 50px;
  }

  .cc-button {
    height: 50%;
    display: flex;
    font-size: 50px;
    /*.card {
      background-color: rgba(4,49,128,.6);
      color: #08e5ff;
      height: 70px;
      width: 70px;
      font-size: 45px;
      font-weight: bold;
      line-height: 70px;
      text-align: center;
      margin: 10px;
    }*/
  }

  .cc-main-container {
    position: relative;
    flex: 1;
    display: flex;

    .ccmc-middle {
      width: 50%;
      height: 90%;

      .active-ring-name {
        font-size: 20px !important;
      }
    }

    .ccmc-left, .ccmc-right {
      width: 25%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      font-size: 24px;

      span {
        font-size: 40px;
        font-weight: bold;
      }

      .station-info {
        height: 80px;
        display: flex;
        align-items: center;
      }
    }

    .ccmc-left {
      align-items: flex-end;

      span {
        margin-left: 20px;
      }
    }

    .ccmc-right {
      align-items: flex-start;

      span {
        margin-right: 20px;
      }
    }
  }

  .label-tag {
    position: absolute;
    width: 500px;
    height: 30px;
    bottom: 10px;
    left: 50%;
    transform: translateX(-50%);
  }
}
</style>
