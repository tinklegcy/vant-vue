<template>
  <div>
    <div :ref="id" :class="className" :style="{height:height,width:width}"></div>
  </div>
</template>

<script>
import echarts from 'echarts'
import resize from "@/components/Charts/mixins/resize";
import theme from "@/assets/echartTheme/macarons.json"
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
      default: "300px"
    },
    data: {
      type: Object,
      default: {}
    }
  },
  name: "",
  data() {
    return {
      chart1: "",
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
        this.chart1.setOption(this.chartOpt, true);
      },
      deep: true
    }
  },
  methods: {
    //数据图初始化
    initChart() {
      const this_ = this;
      echarts.registerTheme('walden', theme)
      this.chart1 = echarts.init(this.$refs[this.id],'walden');
      var option = {
        title: {
          text: ""
        },

        tooltip: {
          trigger: "axis",
          // axisPointer: {
          //   type: "line"
          // },
          axisPointer: {
            type: 'cross',
            label: {
                backgroundColor: '#6a7985'
            }
        },
          formatter: function(item) {
            let list = [];
            for (var i = 0; i < item.length; i++) {
              list.push(
                item[i].marker + item[i].seriesName + ":" + item[i].value
              );
            }
            // console.log(item[0])
            return (
              '<div class="showBox">' +
              this_.utils.formatDate(item[0].axisValue) +
              this_.utils.Week(item[0].axisValue) +
              "<br/>" +
              list.join("<br>") +
              "</div>"
            );
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
        // toolbox: {
        //   feature: {
        //     saveAsImage: {}
        //   }
        // },
        xAxis: {
          type: "category",
          boundaryGap: false,
          data: []
        },
        yAxis: {
          type: "value"
        },
        series: []
      };
      this.chartOpt = option;
      this.chart1.setOption(this.chartOpt, true);
    }
  }
};
</script>

<style scoped>
</style>
