<template>
  <div class="matrix">
    <div class="row" v-for="(row,y) in numbers" :key="y">
      <div class="cell" v-for="(cell,x) in row" :key="x">
        <span v-if="selected[y][x]">
          x
        </span>
        <a v-else @click="select(x,y)">
          {{ cell }}
        </a>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import NumberCheck from './NumberCheck.vue';

@Component
export default class YellowScore extends Vue {
  private numbers = [
    [3,6,5,0],
    [2,1,0,5],
    [1,0,2,4],
    [0,3,4,6],
  ];
  private selected = [
    [ false, false, false, true],
    [ false, false, true, false],
    [ false, true, false, false],
    [ true, false, false, false],
  ]
  public select(x:number, y:number ){
    this.selected[y].splice(x, 1, true)
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.matrix {
  background: darkorange;
  border-radius: 0.5rem;
  border: solid 2px yellow;
  .row {
    display: flex;
    flex-direction: row;
  }
  .cell {
    padding: 1rem;
    margin: 1rem;
    background: white;
    border-radius: 0.5rem;
  }
}
</style>
