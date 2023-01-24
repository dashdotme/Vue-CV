<script setup lang="ts">
import Section from "../ContentTemplate.vue";
import ContentItem from "../ContentItem.vue";

const props = defineProps<{
  useRealData: boolean;
}>();

const testimonials: {
  name: string;
  title: string;
  employer: string;
  testimony: string;
}[] = [
  {
    name: "",
    title: "",
    employer: "",
    testimony:
      "If everyone gave feedback like Dash does from day 1 of programming courses, I think the average skill level of every programmer globally would double in a year.",
  },
  {
    name: "",
    title: "",
    employer: "",
    testimony:
      "Thank you Dash, I think you are one of the most detailed and thoughtful markers I've ever experienced. ...I was kind of dreading these results. But there was so much useful information in there, and I feel motivated once more to have read through all the feedback. So thank you, so much.",
  },
];

const redacted: string = "Redacted";

</script>

<template>
  <Section>
    <template #heading>Student Testimonials</template>
    <ContentItem
      v-for="(item, index) in testimonials"
      :key="index"
      :class="{ last: index == testimonials.length - 1 }"
    >
      <template #title> {{ useRealData ? item.name : redacted }}</template>
      <template #period> {{ useRealData ? item.title : redacted }}</template>
      <template #employer> {{ useRealData ? item.employer : redacted }}</template>
      <template #detail>
        <p>
          {{ item.testimony }}
        </p>
      </template>
    </ContentItem>
  </Section>
</template>
