<template>
  <div class="left-chart-3">
    <div class="lc3-header">
      <canvas id="graph-title" ref="graph-title" style="width: 100%; height: 24px;" ></canvas>
    </div>
    <dv-capsule-chart class="lc3-chart" :config="config" style="width:100%; height:300px;" />
  </div>
</template>

<script>
  import CRender from '@jiaminghi/c-render'
export default {
  name: 'LeftChart3',
  components: {
    CRender,
  },
  data () {
    return {
      config: {
        data: [
          {
            name: '价格波动风险',
            value: 78
          },
          {
            name: '流动性风险',
            value: 54
          },
          {
            name: '投机性风险',
            value: 123
          },
          {
            name: '套期保值风险',
            value: 167
          },
          {
            name: '交易履约风险',
            value: 77
          }
        ],
        colors: ['#00baff', '#3de7c9', '#fff', '#ffc530', '#469f4b'],
      }
    }
  },
  mounted() {
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
      const centerPoint = [w / 2, h / 2];
      const graphTitle = {
        name: 'text',
        animationCurve: 'easeOutBounce',
        hover: true,
        drag: true,
        shape: {
          content: '交易商风险系数',
          position: centerPoint,
        },
        style: {
          fill: '#9ce5f4',
          fontSize: 18,
          shadowBlur: 0,
          shadowColor: '#66eece',
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
.left-chart-3 {
  width: 100%;
  height: 33%;
  display: flex;
  flex-direction: column;

  .lc3-header {
    margin-top: 10px;
  }

  .lc3-chart {
    flex: 1;
  }
}
</style>
