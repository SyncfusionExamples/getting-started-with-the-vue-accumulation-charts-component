<template>
  <div id="app">
    <ejs-accumulationchart :title="chartTitle" :legendSettings="chartLegendSettings"
    :tooltip="chartTooltip">
      <e-accumulation-series-collection>
        <e-accumulation-series :dataSource="chartData" xName="browser" 
        yName="usersCount" :dataLabel="chartDatalabel" type="Funnel">
        </e-accumulation-series>
      </e-accumulation-series-collection>
    </ejs-accumulationchart>
  </div>
</template>

<script>
import Vue from "vue";
import { AccumulationChartPlugin, AccumulationDataLabel, AccumulationTooltip, PyramidSeries,
FunnelSeries, AccumulationLegend } from "@syncfusion/ej2-vue-charts";
Vue.use (AccumulationChartPlugin);

export default {
  data() {
    return {
      chartTooltip : {
        enable : true
      },
      chartLegendSettings : {
        visible : true
      },
      chartDatalabel : {
        visible : true
      },
      chartTitle : 'Mobile Browser Statistics',
      chartData : [
        { browser : "Chrome", usersCount : 37},
        { browser : "UC Browser", usersCount : 17},
        { browser : "Safari",  usersCount : 19 },
        { browser : "Others", usersCount : 4 },
        { browser : "Opera", usersCount : 11 }
      ]

    };
  },
  provide : {
    accumulationchart : [ AccumulationDataLabel, AccumulationLegend, AccumulationTooltip,
    PyramidSeries, FunnelSeries ]
  }
};
</script>

<style>

</style>
