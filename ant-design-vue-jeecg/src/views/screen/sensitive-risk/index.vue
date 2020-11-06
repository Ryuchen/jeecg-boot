<template>
  <div id="sensitive-risk-view">
    <dv-full-screen-container>
      <top-header />
      <div class="main-content">
        <div class="decoration-content-top">
          <dv-decoration-3 style="width:250px;height:30px;" />
          <redirect-button/>
          <dv-decoration-3 style="width:250px;height:30px;" />
        </div>
        <div class="decoration-content">
          <dv-border-box-11 title="交易风险智能分析与预警平台" :titleWidth=320 >
            <div class="content">
              <div class="left-chart-container">
                <dv-border-box-3>
                  <div class="left-chart-top">
                    <risk-left-chart-1 />
                  </div>
                  <div class="left-chart-bottom">
                    <Left-Chart-3 />
                  </div>
                </dv-border-box-3>
              </div>
              <div class="right-main-container">
                <div class="rmc-top-container">
                  <center-cmp />
                </div>
                <div class="rmc-bottom-container">
                  <bottom-charts/>
                </div>
              </div>
            </div>
          </dv-border-box-11>
        </div>
        <div class="decoration-content-bottom">
          <dv-decoration-8 style="width:300px;height:50px;" />
          <dv-decoration-8 :reverse="true" style="width:300px;height:50px;" />
        </div>
      </div>
    </dv-full-screen-container>
  </div>
</template>

<script>
import RiskLeftChart1 from './parts/LeftChart1'
import LeftChart3 from './parts/LeftChart3'
import CenterCmp from './parts/CenterCmp'
import RightChart1 from './parts/RightChart1'
import RightChart2 from './parts/RightChart2'
import BottomCharts from './parts/BottomCharts'
import topHeader from './parts/topHeader'
import redirectButton from './parts/redirectButton'

export default {
  name: 'sensitiveRiskView',
  components: {
    topHeader,
    redirectButton,
    RiskLeftChart1,
    LeftChart3,
    CenterCmp,
    RightChart1,
    RightChart2,
    BottomCharts
  },
  data () {
    return {}
  }
}
</script>

<style lang="less">
#sensitive-risk-view {
  position: relative;
  width: 100%;
  height:100%;
  color: #fff;

  #dv-full-screen-container {
    background-image: url('img/bg.png');
    background-size: 100% 100%;
    box-shadow: 0 0 3px blue;
    display: flex;
    flex-direction: column;
  }

  .main-content {
    position: relative;
    flex: 1;
    display: flex;
    flex-direction: column;
    padding: 0 10px 20px 10px;

    .decoration-content-top {
      display: flex;
      justify-content: space-between;
    }

    .decoration-content {
      height: 100%;
      flex: 1;
      display: flex;
      padding: 0 20px;

      .content {
        position: relative;
        flex: 1;
        display: flex;
        flex-direction: row;
        width: 100%;
        height: 100%;
        padding: 50px 20px 30px 20px;

        .left-chart-container {
          position: relative;
          flex: 1 1 auto;
          flex-direction: column;
          width:30%;
          height:100%;

          .left-chart-top{
            height: 40%;
          }
          .left-chart-bottom{
            height:50%;
          }
        }

        .right-main-container {
          width: 70%;
          height: 100%;
          padding-left: 5px;
          display: flex;
          flex-direction: column;
          box-sizing: border-box;

          .rmc-top-container {
            height: 65%;
          }

          .rmc-bottom-container {
            height: 35%;
            display: flex;
            flex-direction: row;
          }
        }
      }
    }

    .decoration-content-bottom {
      display: flex;
      justify-content: space-between;
    }
  }
}
</style>
