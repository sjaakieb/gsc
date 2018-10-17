<template>
  <div>
      <p>Round : {{ round }}</p>
      <input type="button" @click="nextRound" value="next">
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class RoundCounter extends Vue {
  private round: number = 1 ;

 // Component methods can be declared as instance methods
  public nextRound(): void {
    this.round++;
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
