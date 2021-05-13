<template>
  <div>
    <h1>About Component</h1>
    <h2>\{{about}}</h2>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import Component from 'vue-class-component';
import { Watch, Prop } from 'vue-property-decorator';

@Component({})
export default class AboutComponent extends Vue {
  @Prop({type: String, default: 'watch out, this is required', required: true})
  public about: string = "";

  @Watch('about')
  log(data: string) {
    console.warn(data);
    console.warn(this.about);
  }
}

</script>
