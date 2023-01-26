<script setup lang="ts">
import Section from "../templates/ContentTemplate.vue";
import ContentItem from "../templates/ContentItem.vue";

const aboutItems: string[] = [
  "Earned my school's 'dux' title and scholarship offers a long time ago, getting perfect marks in economics.",
  "Thought I'd be a writer growing up. Regularly wrote for the paper during school, drafting a novella and many bits and pieces by 20. Programming became the practical outlet for those skills. ",
  "Newly passionate second-brain-er, after discovering 'Obsidian.md'. Love creating and documenting process.",
];
</script>

<template>
  <Section>
    <template #heading>About</template>
    <ContentItem :class="{ last: true }">
      <template #detail>
        <div class="about">
          <ul class="sentences">
            <li v-for="(item, index) in aboutItems" :key="index">
              {{ item }}
            </li>
          </ul>
        </div>
      </template>
    </ContentItem>
  </Section>
</template>

<style scoped>
.sentences li {
  padding-inline-start: 0px;
  list-style: circle;
  border-bottom: none;
  line-height: 18px;
  padding-top: 0.25em;
  padding-bottom: 0.25em;
}
</style>
