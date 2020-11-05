<template>
  <div id="gauge-chart-region">
    <div class="region-title">
      <canvas id="graph-title" ref="graph-title" style="width: 100%; height: 24px;"></canvas>
    </div>
    <dv-charts :option="option" style="width:100%; height:300px;" />
  </div>
</template>

<script>
import CRender from '@jiaminghi/c-render'

export default {
  name: "gaugeChart",
  components: {
    CRender,
  },
  data() {
    const data = [
      { name: 'A', value: 25, gradient: ['#03c2fd', '#1ed3e5', '#2fded6'] },
      { name: 'B', value: 45, gradient: ['#03c2fd', '#1ed3e5', '#2fded6'], radius: '65%' },
      { name: 'C', value: 65, gradient: ['#03c2fd', '#1ed3e5', '#2fded6'], radius: '55%' },
      { name: 'D', value: 35, gradient: ['#03c2fd', '#1ed3e5', '#2fded6'], radius: '45%' },
      { name: 'E', value: 25, gradient: ['#03c2fd', '#1ed3e5', '#2fded6'], radius: '35%' },
      { name: 'F', value: 35, gradient: ['#03c2fd', '#1ed3e5', '#2fded6'], radius: '25%' },
      { name: 'G', value: 25, gradient: ['#03c2fd', '#1ed3e5', '#2fded6'], radius: '15%' }
    ];
    return {
      cRender: null,
      option: {
        series: [
          {
            type: 'gauge',
            radius: '75%',
            splitNumber: 10,
            startAngle: -Math.PI / 2,
            endAngle: Math.PI * 1.5,
            arcLineWidth: 5,
            data: data,
            axisLabel: {
              show: false
            },
            axisTick: {
              show: false
            },
            pointer: {
              show: false
            },
            dataItemStyle: {
              lineCap: 'round'
            },
            backgroundArc: {
              show: false
            },
            details: {
              show: true,
              formatter: '{name}占比{value}%',
              position: 'start',
              offset: [-10, 0],
              style: {
                fill: '#1ed3e5',
                fontSize: 13,
                textAlign: 'right',
              }
            }
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
#gauge-chart-region {
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