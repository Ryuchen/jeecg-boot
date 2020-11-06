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
  export default {
    name: 'CenterCmp',
    data () {
      return {

        option1: {
          title: {
            text: '大连商品交易所11月豆一价格实际走势与预测走势',
            style: {
              fill: '#ffffff',
              fontSize: 17,
              fontWeight: 'bold',
              textAlign: 'center',
              textBaseline: 'bottom'
            }
          },
          legend: {
            data: [{
              name: '实际走势',
            },
              {
                name: '预测走势',
                color: '#ff9f7f'
              }],
            textUnselectedStyle: {
              fontFamily: 'Arial',
              fontSize: 13,
              fill: '#a3a2a3'
            },
            textStyle: {
              fontFamily: 'Arial',
              fontSize: 15,
              fill: '#fff'
            }
          },
          xAxis: {
            name: '日期',
            nameTextStyle: {
              fill: '#ffffff',
              fontSize: 15
            },
            data: ['', '11.2', '', '', '11.5', '', '','','','11.10',
              '','','','','11.15','','','','','11.20',
              '','','','','11.25','','','','','11.30'],
            dataByText:
              {
                fill: '#ffffff',
                fontSize: 15
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
                  fontSize: 15,
                }
              }
          },
          yAxis: {
            name: '价格/元/100kg',
            data: 'value',
            min: 4800,
            max: 5700,
            interval:180,
            dataByText:
              {
                fill: '#ffffff',
                fontSize: 15
              },
            nameTextStyle: {
              fill: '#ffffff',
              fontSize: 15,
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
                  fontSize: 15,
                }
              }
          },
          series: [
            {
              name: '实际走势',
              data: [, 5173.83, 5141.67, 5171.33, 5235.67, ],
              type: 'line',
              stack: 'a',
              fill: {
                show: true
              },
              lineStyle:{
                lineWidth: 3
              }
            },
            {
              name: '预测走势',
              data: [,5100, 5130, 5150, 5190, 5220, 5220,
                5220, 5250, 5230, 5260, 5280, 5300, 5300,
                5300, 5250, 5240, 5260, 5300, 5280, 5280,
                5280, 5300, 5340, 5280, 5260, 5270, 5270,
                5270, 5290],
              type: 'line',
              stack: 'b',
              fill: {
                show: true
              },
              lineStyle: {
                stroke: '#ff9f7f',
                lineWidth: 3
              },
              linePoint: {
                style: {
                  stroke: '#ff9f7f'
                }
              }
            }
          ]
        },

        option2: {
          title: {
            text: '大连商品交易所11月豆二价格实际走势与预测走势',
            style: {
              fill: '#ffffff',
              fontSize: 17,
              fontWeight: 'bold',
              textAlign: 'center',
              textBaseline: 'bottom'
            }
          },
          legend: {
            data: [{
              name: '实际走势',
            },
              {
                name: '预测走势',
                color: '#ff9f7f'
              }],
            textUnselectedStyle: {
              fontFamily: 'Arial',
              fontSize: 13,
              fill: '#a3a2a3'
            },
            textStyle: {
              fontFamily: 'Arial',
              fontSize: 15,
              fill: '#fff'
            }
          },
          xAxis: {
            name: '日期',
            nameTextStyle: {
              fill: '#ffffff',
              fontSize: 15
            },
            data: ['', '11.2', '', '', '11.5', '', '','','','11.10',
              '','','','','11.15','','','','','11.20',
              '','','','','11.25','','','','','11.30'],
            dataByText:
              {
                fill: '#ffffff',
                fontSize: 15
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
                  fontSize: 15,
                }
              }
          },
          yAxis: {
            name: '价格/元/100kg',
            data: 'value',
            min: 3400,
            max: 4000,
            interval:120,
            dataByText:
              {
                fill: '#ffffff',
                fontSize: 15
              },
            nameTextStyle: {
              fill: '#ffffff',
              fontSize: 15,
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
                  fontSize: 15,
                }
              }
          },
          series: [
            {
              name: '实际走势',
              data: [, 3689.89, 3673.5, 3702.3, 3782, ],
              type: 'line',
              stack: 'a',
              fill: {
                show: true
              },
            },
            {
              name: '预测走势',
              data: [,3700, 3720, 3730, 3750, 3770, 3770,
                3770, 3750, 3730, 3740, 3760, 3740, 3740,
                3740, 3750, 3780, 3760, 3770, 3730, 3730,
                3730, 3740, 3760, 3780, 3800, 3790, 3790,
                3790, 3780],
              type: 'line',
              stack: 'b',
              fill: {
                show: true
              },
              lineStyle: {
                stroke: '#ff9f7f',
              },
              linePoint: {
                style: {
                  stroke: '#ff9f7f'
                }
              }
            }
          ]
        },

        option3: {
          title: {
            text: '大连商品交易所11月豆粕价格实际走势与预测走势',
            style: {
              fill: '#ffffff',
              fontSize: 17,
              fontWeight: 'bold',
              textAlign: 'center',
              textBaseline: 'bottom'
            }
          },
          legend: {
            data: [{
              name: '实际走势',
            },
              {
                name: '预测走势',
                color: '#ff9f7f'
              }],
            textUnselectedStyle: {
              fontFamily: 'Arial',
              fontSize: 13,
              fill: '#a3a2a3'
            },
            textStyle: {
              fontFamily: 'Arial',
              fontSize: 15,
              fill: '#fff'
            }
          },
          xAxis: {
            name: '日期',
            nameTextStyle: {
              fill: '#ffffff',
              fontSize: 15
            },
            data: ['', '11.2', '', '', '11.5', '', '','','','11.10',
              '','','','','11.15','','','','','11.20',
              '','','','','11.25','','','','','11.30'],
            dataByText:
              {
                fill: '#ffffff',
                fontSize: 15
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
                  fontSize: 15,
                }
              }
          },
          yAxis: {
            name: '价格/元/100kg',
            data: 'value',
            min: 2800,
            max: 3500,
            interval:140,
            dataByText:
              {
                fill: '#ffffff',
                fontSize: 15
              },
            nameTextStyle: {
              fill: '#ffffff',
              fontSize: 15,
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
                  fontSize: 15,
                }
              }
          },
          series: [
            {
              name: '实际走势',
              data: [, 3119.38, 3120.5, 3140.25, 3212.63, ],
              type: 'line',
              stack: 'a',
              fill: {
                show: true
              },
            },
            {
              name: '预测走势',
              data: [,3100, 3130, 3150, 3170, 3190, 3190,
                3190, 3200, 3210, 3200, 3180, 3190, 3190,
                3190, 3170, 3180, 3160, 3170, 3160, 3160,
                3160, 3150, 3170, 3180, 3200, 3210, 3210,
                3210, 3200],
              type: 'line',
              stack: 'b',
              fill: {
                show: true
              },
              lineStyle: {
                stroke: '#ff9f7f',
              },
              linePoint: {
                style: {
                  stroke: '#ff9f7f'
                }
              }
            }
          ]
        },

        option4: {
          title: {
            text: '大连商品交易所11月豆油价格实际走势与预测走势',
            style: {
              fill: '#ffffff',
              fontSize: 17,
              fontWeight: 'bold',
              textAlign: 'center',
              textBaseline: 'bottom'
            }
          },
          legend: {
            data: [{
              name: '实际走势',
              },
              {
                name: '预测走势',
                color: '#ff9f7f'
              }],
            textUnselectedStyle: {
              fontFamily: 'Arial',
              fontSize: 13,
              fill: '#a3a2a3'
            },
            textStyle: {
              fontFamily: 'Arial',
              fontSize: 15,
              fill: '#fff'
            }
          },
          xAxis: {
            name: '日期',
            nameTextStyle: {
              fill: '#ffffff',
              fontSize: 15
            },
            data: ['', '11.2', '', '', '11.5', '', '','','','11.10',
              '','','','','11.15','','','','','11.20',
              '','','','','11.25','','','','','11.30'],
            dataByText:
              {
                fill: '#ffffff',
                fontSize: 15
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
                  fontSize: 15,
                }
              }
          },
          yAxis: {
            name: '价格/元/100kg',
            data: 'value',
            min: 6800,
            max: 7400,
            interval:120,
            dataByText:
              {
                fill: '#ffffff',
                fontSize: 15
              },
            nameTextStyle: {
              fill: '#ffffff',
              fontSize: 15,
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
                  fontSize: 15,
                }
              }
          },
          series: [
            {
              name: '实际走势',
              data: [, 7010, 7036.86, 7179.5, 7148.57, ],
              type: 'line',
              stack: 'a',
              fill: {
                show: true
              }
            },
            {
              name: '预测走势',
              data: [,7100, 7130, 7150, 7190, 7220, 7220,
                7220, 7200, 7180, 7190, 7170, 7180, 7180,
                7180, 7190, 7160, 7140, 7170, 7130, 7130,
                7130, 7150, 7180, 7210, 7220, 7210, 7210,
                7210, 7200],
              type: 'line',
              stack: 'b',
              fill: {
                show: true
              },
              lineStyle: {
                stroke: '#ff9f7f',
              },
              linePoint: {
                style: {
                  stroke: '#ff9f7f'
                }
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
  margin: 0;
  padding: 8px;
  display: block;
  flex-direction: column;

  .cc-top {
    height: 50%;
    display: flex;
  }

  .cc-button {
    height: 50%;
    display: flex;
  }
}
</style>
