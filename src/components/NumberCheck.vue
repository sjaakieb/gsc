<template>
  <div class="cell" @click="select()">
    <span v-if="value">
      x
    </span>
    <a v-else>
      {{ number }}
    </a>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class NumberCheck extends Vue {

  @Prop({required: false, default: false})
  private value!: boolean;

  @Prop({required: true})
  private number!: number;

  public select() {
    if (!this.value) {
      this.$emit('update', true);
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.cell {
  background: white;
  cursor: pointer;
}
</style>
