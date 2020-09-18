<template>
  <div class="min-h-screen relative">
    <ul class="grid grid-cols-11 sticky inset-0">
      <li></li>
      <li
        v-for="key in Object.keys(palette[Object.keys(palette)[0]])"
        :key="key"
        class="flex items-end justify-center py-3"
      >
        {{ key }}
      </li>
    </ul>
    <ul v-for="(hues, color) in palette" :key="color" class="grid grid-cols-11">
      <li class="flex items-center justify-end px-3">
        {{ color }}
      </li>
      <li
        v-for="(hue, key) in hues"
        :key="key"
        :class="[`bg-${color}-${key}`]"
        class="flex items-center justify-center h-32"
      ></li>
    </ul>
  </div>
</template>

<script>
import colors from "./colors";
import { computed, ref } from "vue";

export default {
  name: "App",
  components: {},
  setup() {
    const palette = ref(colors);
    return {
      palette,
    };
  },
};
</script>
