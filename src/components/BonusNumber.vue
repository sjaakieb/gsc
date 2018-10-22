<template>
  <div class="cell" :class="color">
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

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.orange {
  color: white;
  background: orangered;
}
</style>
