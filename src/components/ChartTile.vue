<template>
  <div class="chart-container">
      <div ref="chart" class="e-chart"></div>
  </div>
</template>

<script>

var echarts = require('echarts')
import _ from 'lodash'

export default {
    data () {
        return {
            chart: {}
        }
    },
    mounted () {
        window.chart = this;

        let chart =  echarts.init(this.$refs.chart)

        chart.setOption({
            title: {
            text: 'ECharts introductory example'
            },
            tooltip: {},
            xAxis: {
                data: ['shirt', 'cardign', 'chiffon shirt', 'pants', 'heels', 'socks']
            },
            yAxis: {},
            series: [{
                name: 'sales',
                type: 'bar',
                data: [5, 20, 36, 10, 10, 20]
            }]
        }, true)
    
    }
}
</script>

<style lang="scss" scoped>
    .chart-container {
        background-color: black;
        width:500px;
        height: 350px;
    }

    .e-chart {
        width:480px;
        height:330px;
    }
</style>
