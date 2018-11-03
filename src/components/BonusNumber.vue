<template>
  <div class="cell" :class="[color, { selected }]">
    {{number}}
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class NumberCheck extends Vue {

  @Prop({required: true})
  private color!: string;

  @Prop({required: true})
  private number!: number;

  @Prop({required: true})
  private selected!: boolean;

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.orange {
  color: white;
  background: rgba(255,69,0,0.2);
  &.selected {
    background: orangered;
  }  
}
.purple {
  color: white;
  background: pink;
  &.selected {
    background: purple;
  }  
}
</style>
