<template>
  <svg xmlns="http://www.w3.org/2000/svg" version="1" viewBox="0 0 360 360">
    <g :fill="fillColor" :stroke="color" stroke-linejoin="round" stroke-width="20">
      <path d="M75 20l145 145-85 185L10 195z"/>
      <path d="M220 165l130-30L210 10 75 20z"/>
      <path d="M135 350l120-30 95-185-130 30z"/>
    </g>
  </svg>
</template>
<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class CubeIcon extends Vue {
  @Prop({required: false, default: 'black'})
  private fillColor!: string;

  @Prop({required: false, default: 'grey'})
  private color!: string;

}
</script>