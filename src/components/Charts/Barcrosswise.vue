<template>
  <div>
    <div :ref="id" :class="className" :style="{height:height,width:width}"></div>
  </div>
</template>

<script>
import resize from "@/components/Charts/mixins/resize";
export default {
  mixins: [resize],
  props: {
    className: {
      type: String,
      default: "chart"
    },
    id: {
      type: String,
      default: "chart"
    },
    width: {
      type: String,
      default: "100%"
    },
    height: {
      type: String,
      default: "200px"
    },
    data: {
      type: Object,
      default: {}
    }
  },
  name: "Barcrosswise",
  data() {
    return {
      chart: "",
      chartOpt: {}
    };
  },
  mounted() {
    this.initChart();
  },
  watch: {
    data: {
      handler(newVal, oldVal) {
        Object.assign(this.chartOpt, this.data);
        this.chart.setOption(this.chartOpt, true);
      },
      deep: true
    }
  },
  methods: {
    //数据图初始化
    initChart() {
      const this_ = this;
      this.chart = this.$echarts.init(this.$refs[this.id]);
      var option = {
        title: {
          text: "",
          subtext: ""
        },
        tooltip: {
          trigger: "axis",
          axisPointer: {
            type: "shadow"
          }
        },
        legend: {
          data: []
        },
        grid: {
          left: "3%",
          right: "4%",
          bottom: "3%",
          containLabel: true
        },

        xAxis: {
          show: false,
          type: "value",
          boundaryGap: [0, 0.01]
        },
        yAxis: {
          type: "category",
          data: []
        },
        series: [
          {
            name: "2012年",
            type: "bar",
            data: [],
            barWidth: 30 //柱图宽度
          }
        ]
      };
      Object.assign(this.chartOpt, option);
      //   this.chartOpt = option;
      this.chart.setOption(this.chartOpt, true);
    }
  }
};
</script>

<style scoped>
</style>
