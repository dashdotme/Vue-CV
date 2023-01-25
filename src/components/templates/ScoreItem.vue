<script lang="ts" setup>
import { ref, type Ref } from "vue";

const props = defineProps<{
  score: number;
}>();

// allow manual updates
const val: Ref<number> = ref(props.score);
</script>

<template>
  <div class="text-center">
    <v-rating
      v-model="val"
      full-icon="mdi-circle"
      half-icon="mdi-circle-half"
      empty-icon="mdi-circle-outline"
      half-increments
      color="#990003"
      size="18"
    ></v-rating>
  </div>
</template>
