<template>
  <swiper
    :slides-per-view="panelViewItemResponsive($vuetify.display.width) + 0.5"
    :space-between="24"
    :free-mode="true"
    :navigation="getBreakpointValue({ breakpoint: 'mobile' }) ? false : true"
    :mousewheel="{
      forceToAxis: true,
      releaseOnEdges: true,
    }"
  >
    <slot></slot>
  </swiper>
</template>

<script setup lang="ts">
import { panelViewItemResponsive } from "@/helpers/utils";
import { getBreakpointValue } from "@/plugins/breakpoint";
import { onMounted } from "vue";

onMounted(() => {
  document.documentElement.style.setProperty(
    "--swiper-navigation-color",
    "primary",
  );
});
</script>
