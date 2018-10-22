<template>
  <div class="cell" :class="color">
    X
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class NumberCheck extends Vue {

  @Prop({required: true})
  private color!: string;
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.green {
  color:white;
  background: green;
}
.blue {
  color:white;
  background: blue;
}
</style>
