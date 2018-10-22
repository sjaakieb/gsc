<template>
<svg
   xmlns="http://www.w3.org/2000/svg"
   viewBox="0 0 26.451126 26.204112">
    <g transform="translate(-60.45763,-376.18081)">
    <path
        d="m 68.356355,377.881 c 3.156726,1.64149 3.219861,1.70463 3.219861,1.70463 l 2.272843,-2.84106 2.588516,2.77792 3.219861,-1.51522 0.947018,3.8512 3.598669,0.12627 -0.757615,3.59867 3.156727,2.08344 -2.714785,2.90419 2.020305,3.15672 -3.535534,1.13643 0.126269,3.6618 -3.661803,-0.50508 -1.767767,3.40927 -3.030457,-2.27285 -2.77792,2.20971 -1.767767,-3.09359 -3.661803,0.56821 0.06314,-3.59867 -3.409265,-1.57836 1.704632,-3.21986 -2.525381,-2.71479 2.841054,-2.14657 -0.883883,-3.283 3.598668,-0.44194 z"
        :fill="color"
        style="fill-rule:evenodd;stroke:#fffffa;stroke-width:1px;stroke-linecap:butt;stroke-linejoin:miter;stroke-opacity:1" />
    <text
        sodipodi:linespacing="89.999998%"
        id="text4207"
        y="393"
        x="73"
        style="font-style:italic;font-variant:normal;font-weight:normal;font-stretch:normal;font-size:10px;line-height:100%;font-family:FreeSans;-inkscape-font-specification:'FreeSans, Italic';text-align:center;writing-mode:lr-tb;text-anchor:middle"
        xml:space="preserve">{{text}}</text>
</g>
</svg>
</template>
<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class StarIcon extends Vue {
  @Prop({required: false, default: "grey"})
  private color!: string;

  @Prop({required: true})
  private text!: string;

}
</script>