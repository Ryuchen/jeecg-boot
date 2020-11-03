<template>
  <div id="rosepie-chart-region">
    <div class="region-title">
      <canvas id="graph-title" ref="graph-title" style="width: 100%; height: 24px;"></canvas>
    </div>
    <dv-charts :option="option" style="width:100%; height:300px;" />
  </div>
</template>

<script>
import CRender from '@jiaminghi/c-render'

export default {
  name: "rosePieChart",
  components: {
    CRender,
  },
  data() {
    const data = [
      { name: '可口可乐', value: 93 },
      { name: '百事可乐', value: 32 },
      { name: '哇哈哈', value: 65 },
      { name: '康师傅', value: 44 },
      { name: '统一', value: 52 },
    ];
    return {
      cRender: null,
      option: {
        legend: {
          data: ['同比', '环比'],
          textStyle: {
            fontSize: 14,
            fill: '#fff'
          }
        },
        series: [
          {
            name: '同比',
            type: 'pie',
            data: data,
            radius: '30%',
            outsideLabel: {
              show: false
            },
            insideLabel: {
              show: true,
              style: {
                fontSize: 10,
                fill: '#fff',
              }
            }
          },
          {
            name: '环比',
            type: 'pie',
            data: data,
            radius: ['40%', '50%'],
            outsideLabel: {
              show: true,
              style: {
                fontSize: 14,
                textBaseline: 'middle'
              }
            },
          }
        ]
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
#rosepie-chart-region {
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