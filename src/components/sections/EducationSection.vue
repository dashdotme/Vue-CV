<script setup lang="ts">
import Section from "../ContentTemplate.vue";
import ContentItem from "../ContentItem.vue";

const schoolItems: { name: string; degree: string; period: string }[] = [
  {
    name: "Massey University",
    degree: "Computer Science",
    period: "2020 - 2021 <br/> Remote",
  },
  {
    name: "Victoria University of Wellington",
    degree: "Software Engineering",
    period: "2016 - 2017 <br/> Wellington",
  },
];
</script>

<template>
  <Section>
    <template #heading>Education</template>
    <ContentItem
      v-for="(item, index) in schoolItems"
      :key="item.name"
      :class="{ last: index == schoolItems.length - 1 }"
    >
      <template #title>{{ item.name }}</template>
      <template #subtitle>{{ item.degree }}</template>
      <template #period> <span v-html="item.period"></span></template>
    </ContentItem>
  </Section>
</template>

<style scoped>
.content-item h4 {
  text-align: center;
}
</style>
