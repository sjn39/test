<template>
  <div ref="mysankeychart" id="sankeydemo"></div>
</template>

<script>
import * as echarts from "echarts";
export default {
  mounted() {
    let myEcharts = echarts.init(this.$refs.mysankeychart);
    //设置参数
    myEcharts.setOption({
      series: {
        type: "sankey",
        layout: "none",
        emphasis: {
          focus: "adjacency",
        },
        data: [
          {
            name: "a",
          },
          {
            name: "b",
          },
          {
            name: "a1",
          },
          {
            name: "a2",
          },
          {
            name: "b1",
          },
          {
            name: "c",
          },
        ],
        links: [
          {
            source: "a",
            target: "a1",
            value: 5,
          },
          {
            source: "a",
            target: "a2",
            value: 3,
          },
          {
            source: "b",
            target: "b1",
            value: 8,
          },
          {
            source: "a",
            target: "b1",
            value: 3,
          },
          {
            source: "b1",
            target: "a1",
            value: 1,
          },
          {
            source: "b1",
            target: "c",
            value: 2,
          },
        ],
      },
    });
  },
};
</script>

<style>
#sankeydemo {
  width: 1500px;
  height: 500px;
}
</style>
