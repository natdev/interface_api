<template>
  <div id="app">
    <chart-manager/>
    <user/>
    <working-time/>
    <working-times/>
  </div>
</template>

<script>
import ChartManager from './components/ChartManager.vue'
import ClockManager from './components/ClockManager.vue'
import User from './components/User.vue'
import WorkingTime from './components/WorkingTime.vue'
import WorkingTimes from './components/WorkingTimes.vue'

export default {
  name: 'app',
  components: {
    ChartManager,
    ClockManager,
    User,
    WorkingTime,
    WorkingTimes
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
