<template>
  <v-card style="border-radius:10px">
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
        title: {
          text: "Trafik Situs",
          left: "left",
          top: "20",
          left: "20",
        },
        tooltip: {
          trigger: "item",
        },
        legend: {
          orient: "vertical",
          left: "left",
          top: "50",
          left: "20",
        },
        series: [
          {
            type: "pie",
            top: "50",
            radius: "65%",
            center: ["50%", "50%"],
            selectedMode: "single",
            data: [
              { value: 1048, name: "Organic Search" },
              { value: 735, name: "Direct" },
              { value: 580, name: "Social" },
              { value: 580, name: "Other" },
            ],
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
  height: 400px;
}
</style>
