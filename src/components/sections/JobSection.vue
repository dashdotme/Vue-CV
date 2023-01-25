<script setup lang="ts">
import Section from "../templates/ContentTemplate.vue";
import ContentItem from "../templates/ContentItem.vue";

const tutoringBullets: string[] = [
  "Responsible for marking 180 students while maintaining a full-time job and a full-time course load",
  "Received exceptional feedback and offers for further roles",
];

const apiviewBullets: string[] = [
  "Infrastructure to replace MS pipelines, tweaked for simplicity and user-scoped access",
  "File processing module which handles file parsing and storage, deployed as an Azure Container App",
  "End-to-end git actions pipelines, turning source code into live Azure resources via Terraform",
  "Custom, scripted docker image creation, with publication to Azure",
  "Integration fixes and patch set for the open-source repository",
];

const jobDetails: {
  title: string;
  period: string;
  employer: string;
  blurb: string;
  bullets?: string[];
}[] = [
  {
    title: "Founder/Software Engineer",
    period: "2022 - Ongoing",
    employer: "Apiview.io",
    blurb:
      "A startup-in-progress/pet project. We're building a software API review system for teams creating libraries, rather than web API. Based on an open source tool used by Microsoft's Azure SDK teams.<br /><br />Personal works:",
    bullets: apiviewBullets,
  },
  {
    title: "Student Tutor/Marker",
    period: "2021",
    employer: "Massey University",
    blurb:
      "Tutored and graded for the second year introduction to Java and functional programming.",
    bullets: tutoringBullets,
  },
  {
    title: "Builder",
    period: "2019 - 2021",
    employer: "3Sixty Construction",
    blurb:
      "Skilled residential carpentry: renovations, joinery installs, odd jobs.",
  },
];
</script>

<template>
  <Section>
    <template #heading> Recent Roles </template>
    <ContentItem
      v-for="(item, index) in jobDetails"
      :key="index"
      :class="{ last: index == jobDetails.length - 1 }"
    >
      <template #title> {{ item.title }}</template>
      <template #period> {{ item.period }}</template>
      <template #subtitle> {{ item.employer }}</template>
      <template #blurb> <span v-html="item.blurb"></span> </template>
      <template #detail>
        <ul class="bullets">
          <li v-for="(bullet, index) in item.bullets" :key="index">
            {{ bullet }}
          </li>
        </ul>
      </template>
    </ContentItem>
  </Section>
</template>

<style scoped>
.bullets li {
  padding-inline-start: 0px;
  list-style: circle;
  padding-top: 0.25em;
  padding-bottom: 0.25em;
  border-bottom: none;
}
ul.bullets {
  padding-inline-start: 0px;
  padding-left: 2em;
}
</style>
