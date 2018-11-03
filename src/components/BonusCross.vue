<template>
  <div class="cell" :class="[color, { selected }]">
    X
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class NumberCheck extends Vue {

  @Prop({required: true})
  private color!: string;

  @Prop({required: true})
  private selected!: boolean;

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.green {
  color:white;
  background: lightgreen;
  &.selected {
    background: green;
  }
}
.blue {
  color:white;
  background: lightblue;
  &.selected {
    background: blue;
  }
}
.yellow {
  color:white;
  background: lightyellow;
  &.selected {
    background: yellow;
  }
}
</style>
