<template>
  <v-card style="border-radius:10px">
    <h2 class="ml-5 py-5">Membership</h2>
    <div class="d-md-flex justify-md-space-between">
      <h1 class="ml-5">1.200</h1>
      <h4 class="mr-5 ml-5 error--text">-10% dari bulan lalu</h4>
    </div>
    <v-chart
      class="line-chart"
      :option="option"
    />
  </v-card>
</template>

<script>
import * as echarts from "echarts";
import { use } from "echarts/core";
import { CanvasRenderer } from "echarts/renderers";
import { LineChart } from "echarts/charts";
import {
  TitleComponent,
  TooltipComponent,
  LegendComponent,
} from "echarts/components";
import VChart, { THEME_KEY } from "vue-echarts";

use([
  CanvasRenderer,
  TitleComponent,
  TooltipComponent,
  LegendComponent,
  LineChart,
]);

export default {
  components: {
    VChart,
  },
  provide: {
    [THEME_KEY]: "light",
  },

  data() {
    return {
      option: {
        xAxis: {
          type: "category",
          data: [
            "JAN",
            "FEB",
            "MAR",
            "APR",
            "MAY",
            "JUN",
            "JUL",
            "AUG",
            "SEP",
            "OCT",
            "NOV",
            "DES",
          ],
        },
        yAxis: {
          type: "value",
        },
        // title: {
        //   text: "Membership",
        //   subtext: "1.200",
        //   left: "left",
        //   top: "20",
        //   left: "20",
        // },
        series: [
          {
            type: "bar",
            data: [90, 200, 150, 80, 170, 110, 130, 80, 110, 70, 50, 110],

            label: {
              show: false,
              position: "center",
            },
          },
        ],
      },
    };
  },
};
</script>

<style scoped>
.line-chart {
  height: 300px;
}
</style>
