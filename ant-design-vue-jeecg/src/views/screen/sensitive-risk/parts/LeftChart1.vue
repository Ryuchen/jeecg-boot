<template>
  <div class="left-chart-1">
    <div class="lc1-title">大豆当年交易总额
        <div class="card">1</div>
        <div class="card">0</div>
        <div class="card">1</div>
        <div class="card">3</div>
        <div class="card">7</div>
    </div>
      <div class="lc1-header">年同比增长<span>5.5%</span>年环比增长<span>6.7%</span></div>
    <div class="lc1-header">大豆当季交易总额
      <div class="card">3</div>
      <div class="card">2</div>
      <div class="card">6</div>
      <div class="card">8</div>
    </div>
    <div class="lc1-header">季同比增长<span>3.5%</span>季环比增长<span>3.6%</span></div>
    <div class="lc1-header">大豆当月交易总额
      <div class="card">1</div>
      <div class="card">0</div>
      <div class="card">0</div>
      <div class="card">8</div>
    </div>
    <div class="lc1-header">月同比增长<span>3.4%</span>月环比增长<span>4.4%</span></div>
  </div>
</template>

<script>
export default {
  name: 'risk-left-chart-1'
}
</script>

<style lang="less">
.left-chart-1 {
  width: 100%;
  display: flex;
  flex-grow: 0;
  flex-direction: column;
  .lc1-title {
    text-align: center;
    height: 15px;
    display: flex;
    justify-content: left;
    align-items: center;
    font-size: 20px;
    margin-top: 50px;
    margin-left: 50px;
    font-weight: bold;
  }
  .lc1-header {
    font-weight: bold;
    text-align: center;
    height: 15px;
    display: flex;
    justify-content: left;
    align-items: center;
    font-size: 20px;
    margin-left: 50px;
    margin-top: 30px;
  }
  span {
    color: #08e5ff;
    font-weight: bold;
    font-size: 25px;
    margin-left: 10px;
    margin-right: 10px;

  }
    .card {
      background-color: rgba(4,49,128,.6);
      color: #08e5ff;
      height: 35px;
      width: 35px;
      font-size: 25px;
      font-weight: bold;
      line-height: 30px;
      text-align: center;
      margin: 5px;
    }
}
</style>
