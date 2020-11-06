<template>
  <div class="chart4">
    <dv-charts :option="option" />
  </div>
</template>

<script>
  import Charts from '@jiaminghi/charts'
  function random(max,min){
    return Math.round(Math.random()*(max-min)+min);
  }
  function randomArray(min){
    var str = [];
    for(var i=0;i<10;i++){
      str[i]=random(min+10,min)
    }
    for(var i=10;i<20;i++){
      str[i]=random(min+20,min+10)
    }
    for(var i=20;i<31;i++){
      str[i]=random(min+30,min+20)
    }
    return str;
  }
  export default {
    name: 'chart4',
    data(){
      return{
        option : {
          title: {
            text: '当月大宗商品交易额走势',
            style: {
              fill: '#ffffff',
              fontSize: 17,
              fontWeight: 'bold',
              textAlign: 'center',
              textBaseline: 'bottom'
            }
          },
          legend: {
            data: ['农林牧渔', '能源化工', '金属矿产', '稀贵金属', '文化艺术品'],
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
            data: ['1', '', '', '', '5', '', '','','','10',
              '','','','','15','','','','','20',
              '','','','','25','','','','','','31'],
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
            name: '交易额/万元',
            data: 'value',
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
              name: '农林牧渔',
              data: randomArray(220),
              type: 'line',
              stack: 'a',
              fill: {
                show: true
              }
            },
            {
              name: '能源化工',
              data: randomArray(190),
              type: 'line',
              stack: 'b',
              fill: {
                show: true
              }
            },
            {
              name: '金属矿产',
              data: randomArray(150),
              type: 'line',
              stack: 'c',
              fill: {
                show: true
              }
            },
            {
              name: '稀贵金属',
              data: randomArray(160),
              type: 'line',
              stack: 'd',
              fill: {
                show: true
              }
            },
            {
              name: '文化艺术品',
              data: randomArray(120),
              type: 'line',
              stack: 'e',
              fill: {
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
  .chart4{
    width: 100%;
    height: 100%;
  }
</style>