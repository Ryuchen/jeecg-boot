<template>
  <div class="left-chart-1">
    <div class="lc1-header">大豆本季交易单数</div>
    <div class="cc-details">
      <div class="card">5</div>
      <div class="card">5</div>
      <div class="card">1</div>
      <div class="card">3</div>
      <div class="card">7</div>
    </div>
    <div class="lc1-header">大豆交易商数量</div>
    <div class="cc-details">
      <div class="card">5</div>
      <div class="card">2</div>
      <div class="card">6</div>
      <div class="card">8</div>
    </div>
  </div>
</template>

<script>
export default {
}
</script>

<style lang="less">
.left-chart-1 {
  width: 100%;
  height: 37%;
  display: flex;
  flex-grow: 0;
  flex-direction: column;

  .lc1-header {
    text-align: center;
    height: 40px;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 30px;
    margin-bottom: 20px;
  }

  .cc-details {
    height: 60px;
    display: flex;
    justify-content: center;
    font-size: 16px;
    align-items: center;
  }
    .card {
      background-color: rgba(4,49,128,.6);
      color: #08e5ff;
      height: 35px;
      width: 35px;
      font-size: 20px;
      font-weight: bold;
      line-height: 35px;
      text-align: center;
      margin: 10px;
    }
}
</style>
