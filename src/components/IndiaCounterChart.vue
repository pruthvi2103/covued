<template>
  <div class="row">
<div class="col-md-6 offset-md-3">
    <!-- <div style="width:50%;" class=""> -->
        <canvas ref="myChart" width="1000" height="400"></canvas>

        <!-- <p> {{ chartData[0] }} </p> -->
        <!-- <button @click="getSpecData"></button> -->
        <!-- <p>{{ chartValuesx }}</p> -->
    </div>
    </div>
</template>

<script>
import Chart from 'chart.js';

export default {
  name: 'monthly-sales-chart',
  data(){
      return{
            chartValuesy: [],
            chartValuesx: []

      }
  },
  props: ['chartData'],
  methods:{
      getSpecData(){
          
          for (const x in this.chartData) {
            this.chartValuesy.push(this.chartData[x]['dailyconfirmed'])
              
          }
          for(const x in this.chartData){
            this.chartValuesx.push(this.chartData[x]['date'] + ' 2020')
          }

      }
  },
  mounted() {
    this.getSpecData();
    new Chart(this.$refs.myChart, {
      type: 'line',  // bar,line,doughnut,radar etc
      
      data: {
        labels: this.chartValuesx,
        datasets: [
          {
            
            data: this.chartValuesy,
            backgroundColor: 'rgba(255, 255, 255, 0.1)',
            borderColor: 'rgba(255,0,0,0.8)',
            borderJoinStyle: 'round',
            pointRadius: 2
          }
        ]
      
    },
        options: {
        scales: {
            xAxes: [{
                type: 'time',
                time: {
                  displayformats: {
                          week: 'MMM YYYY'
                  },
                    //unit: 'week'
                },
                gridLines:{display:false},
              ticks: {
        
        maxTicksLimit: 15
    },

            }],
            yAxes:[{
              gridLines:{display:false},
              position: 'right',
            }]
        }
    }


    })//end of charts vals;
    
  }
}
</script>

<style scoped>

</style>