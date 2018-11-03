<template>
  <div class="cell" :class="{ active }">
    +1
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class BonusPlusOne extends Vue {

  @Prop({required: true})
  private active!: boolean;

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.cell {
  color:white;
  background: grey;
  &.active {
    background: black;
  }
}
</style>
