<script setup lang="ts">
import Intro from "../templates/IntroTemplate.vue";
import ContactItem from "../templates/ContactItem.vue";
import PhoneIcon from "../icons/IconPhone.vue";
import MailIcon from "../icons/IconEmail.vue";
import GitIcon from "../icons/IconGithub.vue";
import type { Component } from "vue";
import ProfilePhoto from "@/assets/cv_pic.resized.jpg"

const props = defineProps<{
  useRealData: boolean;
}>();

// Quick messy workaround for easy redaction
const redacted: string = `Redacted`;

const sensitiveContent: string[] = [
  ``,
  ``,
];

const pic = {
  imageRef: new URL(ProfilePhoto, import.meta.url).href,
  class: "pic",
  alt: "Dashiell Vallance",
};

const nameItem: { content: string }[] = [
  { content: "Dashiell Vallance" },
  { content: "(Dash)" },
];

const detailsItem: { icon: Component; content: string }[] = [
  {
    icon: PhoneIcon,
    content: props.useRealData ? sensitiveContent[0] : redacted,
  },
  {
    icon: MailIcon,
    content: props.useRealData ? sensitiveContent[1] : redacted,
  },
  {
    icon: GitIcon,
    content: `<a href="https://github.com/dashdotme">github.com/dashdotme</a>`,
  },
];
</script>

<template>
  <div id="hd">
    <Intro>
      <template #pic>
        <img :src="pic.imageRef" :alt="pic.alt" :class="pic.class" />
      </template>
      <template #name>
        <h2 v-for="(item, index) in nameItem" :key="index">
          {{ item.content }}
        </h2>
      </template>
      <template #details>
        <ContactItem v-for="(item, index) in detailsItem" :key="index">
          <template #icon>
            <component :is="item.icon" />
          </template>
          <h3 v-html="item.content"></h3>
        </ContactItem>
      </template>
    </Intro>
  </div>
</template>

<style scoped>
.pic {
  max-height: 12%;
  max-width: 12%;
  float: left;
  align-items: flex-start;
}

#hd {
  margin: 2em 0 1em 0;
  padding-bottom: 2em;
  border-bottom: 1px solid #ccc;
}
#hd h2 {
  text-transform: uppercase;
  letter-spacing: 2px;
}
</style>
