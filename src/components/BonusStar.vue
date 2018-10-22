<template>
  <div class="cell">
    <Star :color="statusColor" :text="text"/>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import Star from './icons/Star.vue';

@Component({
  components:{
    Star,
  }
}) export default class BonusStar extends Vue {
  @Prop({required: true})
  private active!: boolean;

  @Prop({required: true})
  private color!: string;

  @Prop({required: true})
  private text!: string;

  get statusColor(): string {
    if (this.active) {
      return "red";
    } else {
      return "grey";
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
