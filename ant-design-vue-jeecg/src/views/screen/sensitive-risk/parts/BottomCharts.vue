<template>
  <div class="risk-bottom-chart">
    <dv-border-box-13>
      <v-chart :force-fit="true" height="280" :padding="padding" :data="data" :scale="scale" style="stroke: #fff">
        <v-tooltip />
        <v-legend :custom="true" :clickable="false" :items="legendItems"/>
        <v-view v-for="(item, i) in data" :key="i" :start="getStart(i)" :end="getEnd(i)" :data="[item]" :scale="getScale(item, i)">
          <v-coord type="rect" direction='LB'/>
          <v-axis dataKey="target" :show="false"/>
          <v-axis dataKey="actual" position="right"/>
          <v-point position="title*target" color="#square" shape="line" :size="12" :v-style="style1"/>
          <v-interval position="title*actual" color="#223273" :size="15"/>
          <v-guide type="region" :start="getGuide(item, 0, 'start')" :end="getGuide(item, 0, 'end')"
                   :v-style="style2"/>
          <v-guide type="region" :start="getGuide(item, 1, 'start')" :end="getGuide(item, 1, 'end')"
                   :v-style="style3"/>
          <v-guide type="region" :start="getGuide(item, 2, 'start')" :end="getGuide(item, 2, 'end')"
                   :v-style="style4"/>
          <v-guide type="region" :start="getGuide(item, 3, 'start')" :end="getGuide(item, 3, 'end')"
                   :v-style="style5"/>
          <v-guide type="region" :start="getGuide(item, 4, 'start')" :end="getGuide(item, 4, 'end')"
                   :v-style="style6"/>
        </v-view>
      </v-chart>
    </dv-border-box-13>
  </div>
</template>

<script>
const data = [
  {"title":"价格波动风险", "ranges": [1, 2, 3, 4, 5, 5], "actual": 2.5, "target": 3.5},
  {"title":"流通性风险", "ranges": [1, 2, 3, 4, 5, 5], "actual": 1, "target": 4.0},
  {"title":"投机性风险", "ranges": [1, 2, 3, 4, 5, 5], "actual": 1.2, "target": 3.8},
  {"title":"套期保值风险", "ranges": [1, 2, 3, 4, 5, 5], "actual": 0.5, "target": 4.5},
  {"title":"交易履约风险", "ranges": [1, 2, 3, 4, 5, 5], "actual": 1.5, "target": 3.0}
];

const scale = [{
  dataKey: 'population',
  tickInterval: 5,
}];

const legendItems = [
  {
    value: '正常',
    marker: {symbol: 'square', fill: '#B3E8A7', radius: 5}
  },
  {
    value: '低风险',
    marker: {symbol: 'square', fill: '#A7E8B4', radius: 5}
  },
  {
    value: '中风险',
    marker: {symbol: 'square', fill: '#FFD591', radius: 5}
  },
  {
    value: '高风险',
    marker: {symbol: 'square', fill: '#F18F62', radius: 5}
  },
  {
    value: '应急响应',
    marker: {symbol: 'square', fill: '#F84E4E', radius: 5}
  },
  {
    value: '实际值',
    marker: {symbol: 'square', fill: '#223273', radius: 5}
  },
  {
    value: '告警值',
    marker: {
      symbol: 'line',
      stroke: '#d70000',
      radius: 5
    }
  },
];

let y = 0;
const yGap = 0.1;

export default {
  name: 'riskBottomChart',
  methods: {
    getStart(i) {
      const { y, yGap } = this;
      return {x:0, y: y + i * yGap + i * 0.125};
    },
    getEnd(i) {
      const { y, yGap } = this;
      return {x: 1, y: y + (i+1) * yGap + i * 0.125};
    },
    getScale (item, i) {
      const ranges = item.ranges;
      return [{
        dataKey: 'actual',
        min: 0,
        max: ranges[5],
        nice: false
      }, {
        dataKey: 'target',
        min: 0,
        max: ranges[5],
        nice: false
      }];
    },
    getGuide(viewData, guideIndex, position) {
      const ranges = viewData.ranges;
      const guide = [
        {start: [-1, 0], end:[1, ranges[0]]},
        {start: [-1, ranges[0]], end: [1, ranges[1]]},
        {start: [-1, ranges[1]], end: [1, ranges[2]]},
        {start: [-1, ranges[2]], end: [1, ranges[3]]},
        {start: [-1, ranges[3]], end: [1, ranges[4]]}
      ];
      return guide[guideIndex][position];
    },
  },
  data() {
    return {
      data,
      padding:[40, 80, 40, 160],
      style1:{
        lineWidth: 2
      },
      style2:{
        fill: '#B3E8A7',
        fillOpacity: 0.85
      },
      style3:{
        fill: '#A7E8B4',
        fillOpacity: 0.85
      },
      style4:{
        fill: '#FFD591',
        fillOpacity: 0.85
      },
      style5:{
        fill: '#F18F62',
        fillOpacity: 0.85
      },
      style6:{
        fill: '#F84E4E',
        fillOpacity: 0.85
      },
      scale,
      legendItems,
      y,
      yGap,
    };
  }
};
</script>

<style lang="less">
.risk-bottom-chart {
  width: 100%;
  height: 100%;
  color: #fff;
}
</style>
