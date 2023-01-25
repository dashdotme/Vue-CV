<script setup lang="ts">
import Section from "../templates/ContentTemplate.vue";
import ContentItem from "../templates/ContentItem.vue";

const props = defineProps<{
  useRealData: boolean;
}>();

const refereeItems: {
  name: string;
  title: string;
  contact?: string;
  reference: string;
}[] = [
  {
    name: "",
    title: "",
    reference: "",
  },
  {
    name: "",
    title: "",
    contact:
      "",
    reference: "",
  },
];

const redactedItems: {
  name: string;
  title: string;
  contact?: string;
  reference: string;
}[] = [
  {
    name: "Redacted",
    title: "Redacted",
    reference: `Redacted`,
  },
  {
    name: "Redacted",
    title: "Redacted",
    reference: `Redacted`,
  },
];

const itemsToUse = props.useRealData ? refereeItems : redactedItems;

</script>
<template>
  <Section>
    <template #heading>References</template>
    <ContentItem
      v-for="(item, index) in itemsToUse"
      :key="index"
      :class="{ last: index == itemsToUse.length - 1 }"
    >
      <template #title> {{ item.name }}</template>
      <template #period> {{ item.title }}</template>
      <template #contact v-if="item.contact">
        <p v-html="item.contact"></p>
      </template>
      <template #detail>
        <p v-if="item.contact" v-html="item.contact"></p>
        <p>
          {{ item.reference }}
        </p>
      </template>
    </ContentItem>
  </Section>
</template>
