<template>
  <v-container class="home">
  <v-row>
    <v-col class="col-md-12">
      <v-btn @click="handleClick(0)">
        <v-icon > {{ barIcon }} </v-icon>
      </v-btn>
      <v-btn @click="handleClick(1)">
        <v-icon> {{ lineIcon }} </v-icon>
      </v-btn>
      <v-btn @click="handleClick(2)">
        <v-icon> {{ donutIcon }} </v-icon>
      </v-btn>
    </v-col>
  </v-row>

    <Chart :chartData="chartData" :type="type"></Chart>
  </v-container>
</template>

<script>
// @ is an alias to /src
import Chart from '../components/Chart.vue';
import { mdiChartBar, mdiChartLine, mdiChartDonut } from '@mdi/js';
export default {
  name: "home",
  components: {
    Chart
  },
  data(){
    return {
      chartData: {
        labels: [ 'January', 'February', 'March', 'April', 'May'],
        datasets: [
          {
            label: 'Data One',
            backgroundColor: '#f87979',
            data: [40, 20, 12, 80, 46]
          }
        ]
      },
      barIcon: mdiChartBar,
      lineIcon: mdiChartLine,
      donutIcon: mdiChartDonut,
      type: 'bar'
    }
  },
  methods: {
    handleClick(id){
      if(id === 0){
        this.type = 'bar'
      }else if(id === 1){
        this.type = 'lineC'
      }else if(id === 2){
        this.type = 'doughnut'
      }

// enum = {
//   0: () => { this.type = 'bar'}
// }
      // enum[id]?.()
    }
  }
};
</script>
