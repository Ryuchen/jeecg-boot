<template>
  <div class="lt-content">
    <div class="lt-text">山东省交易所数量</div>
    <div class="lt-numbers">
      <div class="card">3</div>
      <div class="card">4</div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'leftTop'
  }
</script>

<style lang="less">
  .lt-content{
    display: flex;
    box-sizing: border-box;
    align-items: center;


    .lt-text{
      text-align: right;
      height: 40px;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 30px;
      width: 60%;
      margin: 10px;
    }
    .lt-numbers{
      margin: 5px;
      align-items: center;
      display: flex;
      box-sizing: border-box;
      .card{
        width: 40px;
        background-color: rgba(4,49,128,.6);
        color: #08e5ff;
        height: 40px;
        font-size: 30px;
        font-weight: bold;
        line-height: 35px;
        text-align: center;
        margin: 5px;
      }
    }
  }
</style>