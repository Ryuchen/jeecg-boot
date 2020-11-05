<template>
  <div id="scroll-board">
    <dv-scroll-board :config="config" />
  </div>
</template>

<script>
export default {
  name: 'ScrollBoard',
  data () {
    return {
      config: {
        header: ['时间', '交易所', '订货量', '交货量', '商品','商品单价'],
        data: [
          ['2019-07-01','国商商品交易中心有限公司', '80', '99', '牛肉','50'],
          ['2019-07-02','威海国际海洋商品交易中心有限公司', '76', '80', '三文鱼','100'],
          ['2019-07-03','日照大宗商品交易中心有限公司', '88', '90', '辣椒','60'],
          ['2019-07-04','临沂国际商品交易中心有限公司', '90', '90', '橡胶轮胎','500'],
          ['2019-07-05','牡丹国际商品交易中心有限公司', '57', '60', '大豆','30'],
          ['2019-07-06','山东标金投资有限公司', '84', '80', '原木','600'],
          ['2019-07-07','山东鼎丰商品电子交易市场', '68', '70', '钢材','350'],
          ['2019-07-08','山东栖霞苹果电子交易市场', '77', '80', '苹果','15'],
          ['2019-07-09','山东金文电子商务有限公司', '90', '77', '汽油','900'],
          ['2019-07-10','山东海倍电子商务股份有限公司', '86', '96', '纸浆','90']
        ],
        columnWidth: [180, 250],
        align: ['center', 'center', 'center', 'center','center','center'],
        rowNum: 7,
        headerBGC: '#1981f6',
        headerHeight: 45,
        oddRowBGC: 'rgba(0, 44, 81, 0.8)',
        evenRowBGC: 'rgba(10, 29, 50, 0.8)'
      }
    }
  }
}
</script>

<style lang="less">
#scroll-board {
  width: 100%;
  box-sizing: border-box;
  margin-left: 20px;
  height: 100%;
  overflow: hidden;

  .header {
    height: auto;
  }
}
</style>
