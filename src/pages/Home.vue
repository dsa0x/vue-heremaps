<template>
  <div>
    {{ name }}
    <HereMap apiKey="" />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import HereMap from "@/components/HereMap.vue";

@Component({
  components: {
    HereMap
  }
})
export default class Home extends Vue {
  name = "Home";
}
</script>

<style scoped></style>
