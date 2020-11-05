<template>
  <div class="chart1">
    <dv-charts :option="option" />
  </div>
</template>

<script>
  import Charts from '@jiaminghi/charts'
  export default {
    name: 'chart1',
    data(){
      return{
        option : {
          title: {
            text: '各产业交易异常数量',
            style: {
              fill: '#ffffff',
              fontSize: 17,
              fontWeight: 'bold',
              textAlign: 'center',
              textBaseline: 'bottom'
            }
          },
          legend: {
            data: ['农林牧渔', '能源化工','金属矿产','稀贵金属'],
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
            name: '月份',
            nameTextStyle: {
              fill: '#ffffff',
              fontSize: 15
            },
            data: ['一月', '二月', '三月', '四月', '五月', '六月'],
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
            name: '单数/笔',
            data: 'value',
            nameTextStyle: {
              fill: '#ffffff',
              fontSize: 15,
            },
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
          series: [
            {
              name: '农林牧渔',
              data: [50, 56, 30, 38, 45, 40],
              type: 'bar',
              shapeType: 'normal'
            },
            {
              name: '能源化工',
              data: [20, 25, 26, 24, 20, 30],
              type: 'bar',
              shapeType: 'normal'
            },
            {
              name: '金属矿产',
              data: [40, 30, 35, 31, 33, 38],
              type: 'bar',
              shapeType: 'normal'
            },
            {
              name: '稀贵金属',
              data: [20, 25, 24, 28, 16, 24],
              type: 'bar',
              shapeType: 'normal'
            }
          ]
        }
      }
    }
  }
</script>

<style lang="less">
  .chart1{
    width: 100%;
    height: 100%;
  }
</style>