<template>
  <v-app>
    <v-main>
      <CV />
    </v-main>
  </v-app>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import CV from "./components/CV.vue";

export default defineComponent({
  name: "App",

  components: {
    CV,
  },

  data() {
    return {
      //
    };
  },
});
</script>
