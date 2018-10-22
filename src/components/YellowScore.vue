<template>
  <div class="matrix">
    <div class="row">
      <number-check :value="selected[0][0]" @update="select(0,0)" number="3"/>
      <number-check :value="selected[0][1]" @update="select(1,0)" number="6"/>
      <number-check :value="selected[0][2]" @update="select(2,0)" number="5"/>
      <number-check :value="selected[0][3]" @update="select(3,0)" number="0"/>
      <bonus-cross color="blue" />
    </div>
    <div class="row">
      <number-check :value="selected[1][0]" @update="select(0,1)" number="2"/>
      <number-check :value="selected[1][1]" @update="select(1,1)" number="1"/>
      <number-check :value="selected[1][2]" @update="select(2,1)" number="0"/>
      <number-check :value="selected[1][3]" @update="select(3,1)" number="5"/>
      <bonus-number color="orange" number="4"/>
    </div>
    <div class="row">
      <number-check :value="selected[2][0]" @update="select(0,2)" number="1"/>
      <number-check :value="selected[2][1]" @update="select(1,2)" number="0"/>
      <number-check :value="selected[2][2]" @update="select(2,2)" number="2"/>
      <number-check :value="selected[2][3]" @update="select(3,2)" number="4"/>
      <bonus-cross color="green"/>
    </div>
    <div class="row">
      <number-check :value="selected[3][0]" @update="select(0,3)" number="0"/>
      <number-check :value="selected[3][1]" @update="select(1,3)" number="3"/>
      <number-check :value="selected[3][2]" @update="select(2,3)" number="4"/>
      <number-check :value="selected[3][3]" @update="select(3,3)" number="6"/>
      <bonus-fox :active="bonusLines[3]"/>
    </div>
    <div class="row">
      <bonus-star color="yellow" :active="false" text="10"/>
      <bonus-star color="yellow" :active="false" text="14"/>
      <bonus-star color="yellow" :active="false" text="16"/>
      <bonus-star color="yellow" :active="false" text="20"/>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import NumberCheck from './NumberCheck.vue';
import BonusCross from './BonusCross.vue';
import BonusStar from './BonusStar.vue';
import BonusFox from './BonusFox.vue';
import BonusNumber from './BonusNumber.vue';

@Component({
  components: {
    NumberCheck,
    BonusCross,
    BonusFox,
    BonusNumber,
    BonusStar,
  },
})
export default class YellowScore extends Vue {
  private numbers = [
    [3, 6, 5, 0],
    [2, 1, 0, 5],
    [1, 0, 2, 4],
    [0, 3, 4, 6],
  ];
  private selected = [
    [ false, false, false, true],
    [ false, false, true, false],
    [ false, true, false, false],
    [ true, false, false, false],
  ];
  public select(x: number, y: number ) {
    this.selected[y].splice(x, 1, true);
  }

  get bonusLines() {
    return this.selected.map(line => line.every(row => row));
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
}
</style>
