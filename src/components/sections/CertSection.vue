<script setup lang="ts">
import Section from "../templates/ContentTemplate.vue";
import ContentItem from "../templates/ContentItem.vue";

const azCert: { url: string; name: string; period: number } = {
  url: "https://www.credly.com/badges/1de277ca-e830-4274-88ff-0a341fc4d915/embedded",
  name: "Azure Fundamentals",
  period: 2022,
};
</script>

<template>
  <Section>
    <template #heading>Certifications</template>
    <ContentItem :class="{ last: true }">
      <template #title>
        <a :href="azCert.url"> {{ azCert.name }} </a>
      </template>
      <template #period> {{ azCert.period }}</template>
    </ContentItem>
  </Section>
</template>
