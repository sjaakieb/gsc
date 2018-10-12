<template>
  <div class="cell">
    <span v-if="selected">
      x
    </span>
    <a v-else @click="select()">
      {{ number }}
    </a>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class NumberCheck extends Vue {

  @Prop({required: false, default: false})
  selected!: boolean

  @Prop({required:true})
  number!: number

  public select(){
    this.selected = true;
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .cell {
    padding: 1rem;
    margin: 1rem;
    background: white;
    border-radius: 0.5rem;
  }
}
</style>
