<script setup lang="ts">
import Section from "../templates/ContentTemplate.vue";
import TechnicalSubItem from "../templates/TechnicalSubItem.vue";
import TechnicalItem from "../templates/TechnicalItem.vue";
import ScoreItem from "../templates/ScoreItem.vue";

interface TechData {
  type?: number; // used to scale the score component; 1 if 'sub-item' scaling is desired
  header: string;
  score?: number;
  description?: string;
  subItems?: TechData[];
}

const technicalItems: TechData[] = [
  {
    header: "Web knowledge",
    subItems: [
      {
        header: "Backend",
        score: 4,
      },
      {
        header: "Frontend",
        score: 2,
      },
    ],
  },
  {
    header: "Languages Overview",
    subItems: [
      {
        header: "Imperative",
        score: 5,
      },
      {
        header: "Declarative",
        score: 3.5,
      },
      {
        header: "Scripting",
        score: 3,
      },
    ],
  },
  {
    header: "Languages, frameworks and domain-specific tools",
    subItems: [
      {
        header: "Java",
        score: 4.5,
        subItems: [
          {
            header: "Spring Boot",
            score: 4,
          },
        ],
      },
      {
        header: "C#",
        score: 3,
        subItems: [
          {
            header: ".NET Core",
            score: 2,
          },
        ],
      },

      {
        header: "Python",
        score: 3,
      },
      {
        header: "C/C++",
        score: 2.5,
      },
      {
        header: "Javascript",
        score: 3.5,
        subItems: [
          {
            header: "Typescript",
            score: 3,
          },
          {
            header: "Node.js",
            score: 3,
          },
          {
            header: "Express & Nestjs",
            score: 2,
          },
          {
            header: "Vue",
            score: 2.5,
          },
          {
            header: "Mongoose",
            score: 3,
          },
        ],
      },
    ],
  },
  {
    header: "Tools",
    type: 1,
    subItems: [
      {
        header: "VSCode",
        description: "for every language, with Vim",
        score: 4,
      },
      {
        header: "Git",
        description: "CLI, hooks, merges, etc.",
        score: 4,
      },
      {
        header: "Linux (Deb-based)",
        description: "Simple bash scripting, etc.",
        score: 3,
      },
      {
        header: "Markup",
        description: "JSON, YAML, Tex, HTML, etc.",
        score: 4,
      },
    ],
  },
  {
    header: "Storage",
    type: 1,
    subItems: [
      {
        header: "Blob/S3",
        score: 3.5,
      },
      {
        header: "SQL",
        score: 2.5,
      },
      {
        header: "NoSQL",
        score: 2,
      },
    ],
  },
  {
    header: "Infrastructure/deployment",
    type: 1,
    subItems: [
      {
        header: "Azure",
        description: "Templates, RBAC configs, etc.",
        score: 4,
      },
      {
        header: "AWS",
        description: "Basic resource setup",
        score: 2,
      },
      {
        header: "Docker",
        description: "Optimized images, compose",
        score: 3.5,
      },

      {
        header: "Git Actions pipelines",
        description: "Setup, triggers, secrets, etc.",
        score: 3,
      },
      {
        header: "Terraform",
        description: "Composition, state, etc.",
        score: 3,
      },
    ],
  },

];
</script>

<template>
  <Section>
    <template #heading>Technical</template>
    <TechnicalItem v-for="(item, index) in technicalItems" :key="index">
      <template #header> {{ item.header }} </template>
      <TechnicalSubItem
        v-for="(subitem, index) in item.subItems"
        :key="index"
        :class="{ 'scaled-item': item.type === 1 }"
      >
        <template #header> {{ subitem.header }} </template>
        <template #detail v-if="subitem.description">
          {{ subitem.description }}
        </template>
        <template #score v-if="subitem.score">
          <ScoreItem :score="subitem.score!" />
        </template>
        <template #subTools v-if="subitem.subItems">
          <TechnicalSubItem
            v-for="(subsubitem, index) in subitem.subItems"
            :key="index"
          >
            <template #header> {{ subsubitem.header }} </template>
            <p v-if="subsubitem.description">{{ subsubitem.description }}</p>
            <template #score v-if="subsubitem.score">
              <ScoreItem :score="subsubitem.score!" />
            </template>
          </TechnicalSubItem>
        </template>
      </TechnicalSubItem>
    </TechnicalItem>
  </Section>
</template>

<style scoped>
.scaled-item {
  transform: scale(0.85);
}

</style>
