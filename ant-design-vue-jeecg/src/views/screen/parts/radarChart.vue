<template>
  <div id="radar-chart-region">
    <div class="region-title">
      <canvas id="graph-title" ref="graph-title" style="width: 100%; height: 24px;"></canvas>
    </div>
    <dv-charts :option="option" style="width:100%; height:300px;" />
  </div>
</template>

<script>
import CRender from '@jiaminghi/c-render'

export default {
  name: "radarChart",
  components: {
    CRender,
  },
  data() {
    const indicators = [
      { name: '西峡', max: 300 },
      { name: '周口', max: 300 },
      { name: '南阳', max: 300 },
      { name: '驻马店', max: 300 },
      { name: '郑州', max: 300 },
      { name: '洛阳', max: 300 }
    ];
    return {
      cRender: null,
      option: {
        legend: {
          data: ['同比', '环比'],
          textStyle: {
            fontSize: 12,
            fill: '#fff'
          }
        },
        radar: {
          polygon: true,
          indicator: indicators,
          axisLabel: {
            style: {
              fill: '#fff'
            }
          }
        },
        series: [
          {
            name: '同比',
            type: 'radar',
            data: [111, 256, 178, 152, 266, 132],
            label: {
              show: false
            },
            animationCurve: 'easeOutBounce'
          },
          {
            name: '环比',
            type: 'radar',
            data: [222, 245, 220, 130, 240, 100],
            label: {
              show: false
            },
            animationCurve: 'easeOutBounce'
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
#radar-chart-region {
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