<template>
    <div>
        <!-- <Bar v-if="type === 'bar'" :chart-data="chartData" :height="height" /> -->
        <!-- <LineC v-if="type === 'line'" :chart-data="chartData" :height="height" /> -->
        <!-- <Doughnut v-if="type === 'doughnut'" :chart-data="chartData" :height="height" /> -->

        <v-component :is="type" :chart-data="chartData" :height="height"></v-component>
    </div>
    
</template>


<script>
import { Bar, Line as LineC, Doughnut } from 'vue-chartjs/legacy'
import Chart from 'chart.js/auto';

export default {
    name: 'Chart',
    components: {
        bar: Bar,
        lineC: LineC, 
        doughnut: Doughnut
    },
    props: ['chartData', 'type'],
    data(){
    return {
      height: 100,
    }
  }
}
</script>


<style></style>