<template>
  <div>
    <div>
      <bonus-star color="yellow" :active="count>0" text="1"/>
      <bonus-star color="yellow" :active="count>1" text="2"/>
      <bonus-star color="yellow" :active="count>2" text="4"/>
      <bonus-star color="yellow" :active="count>3" text="7"/>
      <bonus-star color="yellow" :active="count>4" text="11"/>
      <bonus-star color="yellow" :active="count>5" text="16"/>
      <bonus-star color="yellow" :active="count>6" text="22"/>
      <bonus-star color="yellow" :active="count>7" text="29"/>
      <bonus-star color="yellow" :active="count>8" text="37"/>
      <bonus-star color="yellow" :active="count>9" text="46"/>
      <bonus-star color="yellow" :active="count>10" text="56"/>
    </div>
    <div class="matrix">
      <div class="row">
        <div>blue+white</div>
        <number-check :value="selected[0][1]" @update="select(1,0)" number="2"/>
        <number-check :value="selected[0][2]" @update="select(2,0)" number="3"/>
        <number-check :value="selected[0][3]" @update="select(3,0)" number="4"/>
        <bonus-number :selected="bonusLines[0]" color="orange" number="5"/>
      </div>
      <div class="row">
        <number-check :value="selected[1][0]" @update="select(0,1)" number="5"/>
        <number-check :value="selected[1][1]" @update="select(1,1)" number="6"/>
        <number-check :value="selected[1][2]" @update="select(2,1)" number="7"/>
        <number-check :value="selected[1][3]" @update="select(3,1)" number="8"/>
        <bonus-cross :selected="bonusLines[1]" color="yellow"/>
      </div>
      <div class="row">
        <number-check :value="selected[2][0]" @update="select(0,2)" number="9"/>
        <number-check :value="selected[2][1]" @update="select(1,2)" number="10"/>
        <number-check :value="selected[2][2]" @update="select(2,2)" number="11"/>
        <number-check :value="selected[2][3]" @update="select(3,2)" number="12"/>
        <bonus-fox :active="bonusLines[2]"/>
      </div>
      <div class="row">
        <div>REROLL</div>
        <bonus-cross :selected="bonusColumns[1]" color="green"/>
        <bonus-number :selected="bonusColumns[2]" color="purple" number="6"/>
        <bonus-plus-one :active="bonusColumns[3]"/>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import NumberCheck from './NumberCheck.vue';
import BonusCross from './BonusCross.vue';
import BonusStar from './BonusStar.vue';
import BonusFox from './BonusFox.vue';
import BonusPlusOne from './BonusPlusOne.vue';
import BonusNumber from './BonusNumber.vue';

@Component({
  components: {
    NumberCheck,
    BonusCross,
    BonusFox,
    BonusNumber,
    BonusStar,
    BonusPlusOne,
  },
})
export default class YellowScore extends Vue {
  private selected = [
    [ true, false, false, false],
    [ false, false, false, false],
    [ false, false, false, false],
  ];
  public select(x: number, y: number ) {
    this.selected[y].splice(x, 1, true);
  }

  get bonusLines() {
    return this.selected.map((line) => line.every((row) => row));
  }

  private countArray(arr:boolean[]):number {
    return arr.reduce((acc, cur) => cur ? acc + 1 : acc, 0);
  }

  private sumArray(arr:number[]):number {
    return arr.reduce((acc, cur) => acc + cur);
  }

  get count() {
    return this.sumArray(this.selected.map(this.countArray))-1;
  }

  get bonusColumns() {
    return [0,1,2,3].map((col) => this.selected.map((line) => line[col])).map((col) => col.every((row) => row));
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.matrix {
  background: darkblue;
  border-radius: 0.5rem;
  border: solid 2px blue;
  .row {
    display: flex;
    flex-direction: row;
  }
}
</style>
