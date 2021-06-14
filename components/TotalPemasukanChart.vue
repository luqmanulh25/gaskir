<template>
  <v-card style="border-radius:10px">
    <h2 class="ml-5 py-5">Total Pemasukan</h2>
    <div class="d-md-flex justify-md-space-between">
      <h1 class="ml-5">Rp 1.500.000</h1>
      <h4 class="mr-5 ml-5 success--text">+30% dari bulan lalu</h4>
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
        //   text: "Total Pemasukan",
        //   left: "left",
        //   top: "20",
        //   left: "20",
        // },
        tooltip: {
          trigger: "item",
        },
        legend: {
          orient: "horizontal",
          left: "left",
          top: "50",
          left: "20",
        },
        series: [
          {
            type: "bar",
            data: [120, 200, 150, 80, 70, 110, 130, 200, 150, 80, 70, 110],
            emphasis: {
              itemStyle: {
                shadowBlur: 10,
                shadowOffsetX: 0,
                shadowColor: "rgba(0, 0, 0, 0.5)",
              },
            },
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
