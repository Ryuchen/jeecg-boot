<template>
  <div class="left-chart-3">
    <div class="lc3-header">
      <canvas id="graph-title" ref="graph-title" style="width: 100%; height: 30px;" ></canvas>
    </div>
      <dv-water-level-pond :config="config" style="width:70%;height:215px;margin-left: 15%;margin-top: 3%"/>
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
        data: [65,44,56,79,50],
        shape: 'roundRect',
        formatter:'{value}%',
        waveHeight:20,
        colors: ['#DD4A68','#a89722','#9ce5f4','#3de7c9','#469f4b'],
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
      const centerPoint = [w / 2, h/2];
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
          fontSize: 26,
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
  margin-top: 3%;

  .lc3-header {
    margin-top: 15px;
  }
}
</style>
