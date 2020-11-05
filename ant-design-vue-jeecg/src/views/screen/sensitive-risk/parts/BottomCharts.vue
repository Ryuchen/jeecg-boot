<template>
  <div id="scroll-board">
    <dv-scroll-board :config="config" />
  </div>
</template>

<script>
  export default {
    name: 'BottomCharts',
    data () {
      return {
        config: {
          header: ['时间', '平台', '风险类型', '等级'],
          data: [
            ['2019-07-01 19:25:00', '交易所A','价格波动风险', '<div class="risk-rate lower">1</div>'],
            ['2019-07-02 17:25:00', '交易所B','合同履约风险',  '<div class="risk-rate low">2</div>'],
            ['2019-07-03 16:25:00', '交易所C','价格波动风险', '<div class="risk-rate middle">3</div>'],
            ['2019-07-04 15:25:00', '交易所F','价格波动风险',  '<div class="risk-rate higher">5</div>'],
            ['2019-07-05 14:25:00', '交易所E','仓单质押风险',  '<div class="risk-rate middle">3</div>'],
            ['2019-07-06 13:25:00', '交易所F','价格波动风险',  '<div class="risk-rate lower">1</div>'],
            ['2019-07-07 12:25:00', '交易所A','价格波动风险',  '<div class="risk-rate high">4</div>'],
            ['2019-07-08 11:25:00', '交易所C','合同履约风险',  '<div class="risk-rate middle">3</div>'],
            ['2019-07-09 10:25:00', '交易所B','合同履约风险',  '<div class="risk-rate middle">3</div>'],
            ['2019-07-10 09:25:00', '交易所D','仓单质押风险',  '<div class="risk-rate low">1</div>']
          ],
          columnWidth: [200, 150, 150,150],
          align: ['center', 'left', 'right', 'right'],
          waitTime: 4000,
          rowNum: 5,
          headerBGC: '#1981f6',
          oddRowBGC: 'rgba(0, 44, 81, 0.8)',
          evenRowBGC: 'rgba(10, 29, 50, 0.8)'
        }
      }
    }
  }
</script>

<style lang="less">
  #scroll-board {
    box-sizing: border-box;
    width: 100%;
    height: 100%;
    overflow: hidden;

    .header {
      height: auto;
    }

    .ceil {
      color: #fff;
      font-weight: 400;

      .risk-rate {
        display: inline-block;
        vertical-align: middle;
        white-space: nowrap;
        text-align: center;
        border-radius: 10px;
        box-shadow: 0 0 0 1px #ccc;
        padding: 2px 6px;
        margin: 0 8px 4px 8px;
        font-size: 10px;
        font-weight: 600;
        line-height: 12px;
      }
      .higher {
        color: #000000;
        background: #f5222d;
      }

      .high {
        color: #000000;
        background: #ff751e;
      }

      .middle {
        color: #000000;
        background: #f8ed28;
      }

      .low {
        color: #000000;
        background: #dbf947;
      }

      .lower {
        color: #000000;
        background: #bdff01;
      }
    }
  }
</style>

