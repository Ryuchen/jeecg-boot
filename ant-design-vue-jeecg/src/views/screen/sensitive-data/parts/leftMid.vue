<template>
  <div class="left-mid">
    <div class="lm-header">
      <canvas id="graph-title" ref="graph-title" style="width: 100%; height: 30px;" ></canvas>
    </div>
    <dv-capsule-chart class="lm-chart" :config="config" style="width:100%; height:300px;" />
  </div>
</template>

<script>
  import CRender from '@jiaminghi/c-render'
  export default {
    name: 'leftMid',
    components: {
      CRender,
    },
    data () {
      return {
        config: {
          data: [
            {
              name: '农林牧渔',
              value: 12
            },
            {
              name: '贵重金属',
              value: 5
            },
            {
              name: '珠宝首饰',
              value: 5
            },
            {
              name: '石油化工',
              value: 9
            },
            {
              name: '其他',
              value: 3
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
            content: '各产业涉及交易所数量',
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
  .left-mid {
    width: 90%;
    height: 33%;
    display: flex;
    flex-direction: column;
    margin-left: 20px;

    .lm-header {
      margin-top: 10px;
    }

    .lm-chart {
      flex: 1;
    }
  }
</style>
