<template>
  <div class="chart-container">
      <div ref="chart" class="e-chart" @click="showInModal()"></div>
  </div>
</template>

<script>

var echarts = require('echarts')
import _ from 'lodash'

export default {
    data () {
        return {
            chart: {},
            options: {
                title: {
                text: 'ECharts introductory example'
                },
                tooltip: {},
                xAxis: {
                    data: ['shirt', 'cardigan', 'chiffon shirt', 'pants', 'heels', 'socks']
                },
                yAxis: {},
                series: [{
                    name: 'sales',
                    type: 'bar',
                    data: [5, 20, 36, 10, 10, 20]
                }]
            }
        }
    },
    methods: {
        showInModal(){
            //make modal resize at the same time.
            this.chart._dom.parentNode.className += ' chart-modal'

            this.chart.resize({
                width: '800px',
                height: '600px'
            })
        }
    },
    mounted () {
        window.chart = this;

        let chart =  echarts.init(this.$refs.chart)

        chart.setOption(this.options, true)

        this.chart = chart;
    }
}
</script>

<style lang="scss" scoped>
    .chart-container {
        background-color: #d9d9d9;
        width:500px;
        height: 350px;
        transition: left 0.4s cubic-bezier(0.23, 1, 0.32, 1), top 0.4s cubic-bezier(0.23, 1, 0.32, 1);
        // transition: all 0.4s ease;
    }

    .e-chart {
        width:450px;
        height:300px;
        position: absolute;
        left: 25px;
        top:25px;
    }

    .chart-modal {
        width: 850px;
        height: 650px;
        position: absolute;
        top: 0;
        left: 0;
        bottom: 0;
        right: 0;
        margin: auto auto;
    }
</style>
