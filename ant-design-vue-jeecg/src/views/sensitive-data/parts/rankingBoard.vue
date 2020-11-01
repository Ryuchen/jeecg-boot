<template>
  <div id="ranking-board">
    <div class="region-title">
      <canvas id="graph-title" ref="graph-title" style="width: 100%; height: 24px;" ></canvas>
    </div>
    <dv-capsule-chart :config="config" style="width:100%; height:300px;" />
  </div>
</template>

<script>
  import CRender from '@jiaminghi/c-render'
export default {
  name: 'RankingBoard',
  components: {
    CRender,
  },
  data () {
    return {
      config: {
        data: [
          {
            name: '交易商弃仓',
            value: 55
          },
          {
            name: '仓库管理不规范',
            value: 120
          },
          {
            name: '贷款准备不足',
            value: 78
          },
          {
            name: '供需不协调',
            value: 66
          },
          {
            name: '合同纠纷',
            value: 80
          }
        ],
        rowNum: 5
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
#ranking-board {
  width: 25%;
  display: flex;
  flex-direction: column;
  box-shadow: 0 0 3px blue;
  background-color: rgba(6, 30, 93, 0.5);
  border-top: 2px solid rgba(1, 153, 209, .5);
  box-sizing: border-box;
  padding: 0 30px;

  .region-title {
    padding-top: 2.4rem;

    #graph-title {
      line-height: 28px;
    }
  }

  .dv-scroll-ranking-board {
    flex: 1;
  }
}
</style>
