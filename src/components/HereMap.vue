/* eslint-disable @typescript-eslint/no-inferrable-types */
<template>
  <div class="heremap">
    <div ref="map" class="map"></div>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from "vue-property-decorator";

@Component({})
export default class App extends Vue {
  map: Record<any, any> = {};
  platform!: any;
  @Prop()
  //   appId: string = "";
  //   appCode: string = "";
  @Prop()
  apiKey!: string;
  lat!: number;
  lng!: number;
  height!: number;
  name = "HereMap";

  created() {
    /* eslint-disable no-undef */
    this.platform = new H.service.Platform({
      apikey: this.apiKey
    });
  }

  mounted() {
    this.map = new H.Map(
      this.$refs.map,
      this.platform.createDefaultLayers().normal.map,
      {
        zoom: 10,
        center: { lng: this.lng, lat: this.lat }
      }
    );
  }
}
</script>

<style scoped>
.map {
  display: flex;
  width: 100%;
  height: 500px;
}
</style>
