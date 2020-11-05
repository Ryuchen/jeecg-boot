<template>
  <div id="capsule-chart-region">
    <div class="region-title">
      <canvas id="graph-title" ref="graph-title" style="width: 100%; height: 24px;" ></canvas>
    </div>
    <dv-capsule-chart :config="config" style="width:100%; height:300px;" />
  </div>
</template>

<script>
import CRender from '@jiaminghi/c-render'

export default {
  name: "capsuleChart",
  components: {
    CRender,
  },
  data() {
    return {
      cRender: null,
      config: {
        data: [
          {
            name: '东北地区',
            value: 100
          },
          {
            name: '华北地区',
            value: 123
          },
          {
            name: '华中地区',
            value: 98
          },
          {
            name: '华东地区',
            value: 75
          },
          {
            name: '华南地区',
            value: 66
          },
          {
            name: '西北地区',
            value: 66
          },
          {
            name: '西南地区',
            value: 66
          },
        ],
        unit: '系数',
        showValue: true
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
    drawTitle (render) {
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
          content: '地区风险系数',
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
  #capsule-chart-region {
    flex: 1 1 auto;
    padding: 16px 8px;

    .region-title {
      padding-top: 2.4rem;

      #graph-title {
        line-height: 28px;
      }
    }
  }
</style>