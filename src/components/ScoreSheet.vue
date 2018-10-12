<template>
  <div>
    <round-counter/>
    <reroll-counter/>
    <extra-die-counter/>
    <yellow-score/>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import RoundCounter from './RoundCounter.vue';
import RerollCounter from './RerollCounter.vue';
import ExtraDieCounter from './ExtraDieCounter.vue';
import YellowScore from './YellowScore.vue';

@Component({
  components: {
    RoundCounter,
    RerollCounter,
    ExtraDieCounter,
    YellowScore,
  },
})
export default class ScoreSheet extends Vue {

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
