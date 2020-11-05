<template>
  <div class="right-chart-2"style="width:700px;" >
    <div class="rc1-header">
      <canvas id="graph-title" ref="graph-title" style="width: 100%; height: 24px;" ></canvas>
    </div>
    <div class="rc1-chart-container">
      <div class="left">
        <div class="left-header">历史风险总数</div>
        <div class="number">267</div>
      </div>
      <dv-charts class="right" :option="option" style="width:350px;" />
    </div>
  </div>
</template>

<script>
  import CRender from '@jiaminghi/c-render'
export default {
  name: 'RightChart2',
  components: {
    CRender,
  },
  data () {
    return {
      option: {
        series: [
          {
            type: 'pie',
            data: [
              { name: '价格波动', value: 93 },
              { name: '流动性', value: 66 },
              { name: '投机性', value: 52 },
              { name: '套期保险', value: 34 },
              { name: '交易履约', value: 22 }
            ],
            radius: ['45%', '65%'],
            insideLabel: {
              show: false
            },
            outsideLabel: {
              labelLineEndLength: 10,
              formatter: '{percent}%\n{name}',
              style: {
                fontSize: 14,
                fill: '#fff'
              }
            }
          }
        ],
        color: ['#00baff', '#3de7c9', '#fff', '#ffc530', '#469f4b']
      }
    }
  },mounted() {
    this.init();
  },
  methods: {
    init() {
      this.cRender = new CRender(this.$refs['graph-title']);
      this.cRender.delAllGraph();
      this.drawTitle(this.cRender);
    },
    drawTitle(render) {
      const {
        area: [w, h],
      } = render;
      const centerPoint = [w /6, h / 2];
      const graphTitle = {
        name: 'text',
        animationCurve: 'easeOutBounce',
        hover: true,
        drag: true,
        shape: {
          content: '交易商风险占比',
          position: centerPoint,
        },
        style: {
          fill: '#ffc',
          fontSize: 18,
          shadowBlur: 0,
          shadowColor: '#ffc530',
          hoverCursor: 'pointer',
          scale: [1, 1],
          rotate: 0,
        }
      }
      render.add(graphTitle);
    }
  }
}
</script>

<style lang="less">
.right-chart-2 {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;

  .rc1-header {
    font-size: 24px;
    font-weight: bold;
    height: 30px;
    line-height: 30px;

    #graph-title {
      line-height: 28px;
    }
  }

  .rc1-chart-container {
    flex: 1;
    display: flex;
  }

  .left {
    width: 30%;
    font-size: 16px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    .left-header {
      margin-top: 10px;
    }
    .number {
      font-size: 34px;
      color: #DD4A68;
      font-weight: bold;
      margin-bottom: 30px;
    }
  }

  .right {
    flex: 1;
    padding-bottom: 20px;
    padding-right: 20px;
    box-sizing:border-box;
  }
}
</style>
