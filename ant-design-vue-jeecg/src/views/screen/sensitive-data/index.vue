<template>
  <div id="data-view">
    <dv-full-screen-container>
      <top-header />
      <div class="main-content">
        <div class="decoration-content-top">
          <redirect-button/>
        </div>
        <div class="main-left-content">
          <dv-border-box-3>
            <div class="ml-top">
              <left-top/>
            </div>
            <div class="ml-mid">
              <left-mid/>
            </div>
            <div class="ml-bottom">
              <rose-chart/>
            </div>
          </dv-border-box-3>
        </div>
        <div class="main-right-content">
          <div class="mr-top">
            <div class="chart-top">
              <div class="chart-top-left">
                <chart1/>
              </div>
              <div class="chart-top-right">
                <chart2/>
              </div>
            </div>
            <div class="chart-bottom">
              <div class="chart-bottom-left">
                <chart3/>
              </div>
              <div class="chart-bottom-right">
                <chart4/>
              </div>
            </div>
          </div>
          <div class="mr-bottom">
            <scroll-board/>
          </div>
        </div>
      </div>
    </dv-full-screen-container>
  </div>
</template>

<script>
  import topHeader from './parts/topHeader'
  import redirectButton from './parts/redirectButton'
  import LeftTop from './parts/leftTop'
  import RoseChart from './parts/roseChart'
  import LeftMid from './parts/leftMid'
  import ScrollBoard from './parts/scrollBoard'
  import Chart1 from './parts/chart1'
  import Chart2 from './parts/chart2'
  import Chart3 from './parts/chart3'
  import Chart4 from './parts/chart4'
  export default {
    name: 'index',
    components: {
      Chart4,
      Chart3,
      Chart1,
      Chart2,
      ScrollBoard,
      LeftMid,
      RoseChart,
      LeftTop,
      topHeader,
      redirectButton
    },
    data () {
      return {}
    },
    methods: {}
  }
</script>

<style lang = "less">
  #data-view {
    width: 100%;
    height: 100%;
    background-color: #030409;
    color: #fff;
  }

  #dv-full-screen-container {
    background-image: url('./img/bg.png');
    background-size: 100% 100%;
    box-shadow: 0 0 3px blue;
    display: flex;
    flex-direction: column;
  }

  .main-content {
    flex: 1;
    display: flex;
    padding-top: 35px;
    flex: border-box;

    .decoration-content-top {
      display: flex;
      justify-content: space-between;
    }
  }

  .main-left-content{
    width:30%;
    height:100%;
    .ml-top{
      height: 10%;
      width: 100%;
      padding-top: 30px;
    }

    .ml-mid {
      height: 40%;
      width: 100%;
    }
    .ml-bottom{
      height:45%;
      width: 100%;
    }
  }

  .main-right-content{
    width: 70%;
    height: 100%;
    .mr-top{
      height:70%;
      .chart-top,.chart-bottom{
        height: 50%;
        width:100%;
        display: flex;
        flex: border-box;
        .chart-top-left,.chart-top-right,.chart-bottom-left,.chart-bottom-right{
          width:50%;
          height:100%
        }
      }
    }
    .mr-bottom{
      height: 30%;
      width: 100%;
    }
  }

</style>