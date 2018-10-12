<template>
  <div>
      <p>Earned: {{ earned }} Checked: {{ used }}</p>
      <input type="button" @click="add" value="add">
      <input type="button" @click="check" :disabled="used >= earned" value="check">
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class RerollCounter extends Vue {
  private earned = 0 ;
  private used = 0 ;

 // Component methods can be declared as instance methods
  public add(): void {
    this.earned++;
  }

  public check(): void {
    this.used++;
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
