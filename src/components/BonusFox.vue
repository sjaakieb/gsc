<template>
  <div class="cell">
    <Fox/>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import Fox from './icons/Fox.vue';

@Component({
  components:{
    Fox,
  }
}) export default class BonusFox extends Vue {

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
