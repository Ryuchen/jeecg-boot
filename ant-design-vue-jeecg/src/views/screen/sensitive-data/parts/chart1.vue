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
            text: '各产业订货量',
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
              data: [115, 120, 123, 135, 166, 177],
              type: 'bar',
              shapeType: 'normal'
            },
            {
              name: '能源化工',
              data: [80, 86, 99, 114, 96, 123],
              type: 'bar',
              shapeType: 'normal'
            },
            {
              name: '金属矿产',
              data: [153, 143, 146, 150, 148, 155],
              type: 'bar',
              shapeType: 'normal'
            },
            {
              name: '稀贵金属',
              data: [113, 115, 102, 122, 109, 115],
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