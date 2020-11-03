<template>
  <div id="sensitive-view">
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
            <div class="left-content">
              <dv-border-box-10>
                <capsule-chart />
                <rose-pie-chart />
              </dv-border-box-10>
            </div>
            <div class="middle-content">
              <div class="middle-content-top">
                <dv-border-box-7>
                  <china-map />
                </dv-border-box-7>
              </div>
              <div class="middle-content-bottom">
                <dv-border-box-7>
                  <scroll-board />
                </dv-border-box-7>
              </div>
            </div>
            <div class="right-content">
              <dv-border-box-10>
                <radar-chart />
                <gauge-chart />
              </dv-border-box-10>
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
import topHeader from './parts/topHeader'
import chinaMap from './parts/chinaMap'
import redirectButton from './parts/redirectButton'
import scrollBoard from './parts/scrollBoard'
import capsuleChart from './parts/capsuleChart'
import rosePieChart from './parts/roseChart'
import radarChart from './parts/radarChart'
import gaugeChart from './parts/gaugeChart'

export default {
  name: 'DataView',
  components: {
    topHeader,
    redirectButton,
    rosePieChart,
    capsuleChart,
    chinaMap,
    scrollBoard,
    radarChart,
    gaugeChart
  },
  data () {
    return {}
  },
  methods: {}
}
</script>

<style lang="less">
#sensitive-view {
  position: relative;
  width: 100%;
  height: 100%;
  color: #fff;

  #dv-full-screen-container {
    background-image: url('./sensitive-data/img/bg.png');
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

        .left-content {
          position: relative;
          flex: 1 1 auto;
          flex-direction: column;
          width: 25%;
          height: 100%;
        }

        .middle-content {
          position: relative;
          flex: 1 1 auto;
          flex-direction: column;
          width: 50%;
          height: 100%;

          .middle-content-top {
            position: relative;
            width: 100%;
            height: 70%;
            padding: 16px;
          }

          .middle-content-bottom {
            height: 30%;
            padding: 16px;
          }
        }

        .right-content {
          flex: 1 1 auto;
          flex-direction: column;
          width: 25%;
          height: 100%;
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
