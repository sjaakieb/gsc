<template>
  <div class="cell">
    <Fox :color="color"/>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import Fox from './icons/Fox.vue';

@Component({
  components: {
    Fox,
  },
}) export default class BonusFox extends Vue {
  @Prop({required: true})
  private active!: boolean;

  get color(): string {
    if (this.active) {
      return 'red';
    } else {
      return 'grey';
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
