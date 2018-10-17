<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <score-sheet/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import ScoreSheet from './components/ScoreSheet.vue';

@Component({
  components: {
    ScoreSheet,
  },
})
export default class App extends Vue {}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  .cell {
    padding: 0.5rem;
    margin: 0.5rem;
    width: 2rem;
    height: 2rem;    
    border-radius: 0.5rem;
    line-height:2rem;
  }
}
</style>
