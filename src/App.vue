<template>
  <div id="app">
    <LineChart :data="chartData" />
  </div>
</template>

<script>
import LineChart from './components/D3.vue';

export default {
  name: 'App',
  components: {
    LineChart
  }
};
</script>
