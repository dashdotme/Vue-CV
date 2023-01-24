<script setup lang="ts">
const props = defineProps<{
  useRealData: boolean;
}>();

const footer: {
  name: string;
  mailto: string;
  email: string;
  phone: string;
  separator: string;
} = {
  name: ``,
  mailto: ``,
  email: ``,
  phone: ``,
  separator: `—`,
};

const redacted: string = `Redacted`;
const empty = "";
</script>

<template>
  <div id="ft">
    <p>
      {{ footer.name }} {{ footer.separator }}
      <a :href="useRealData ? footer.mailto : 'mailto:' + redacted">{{
        useRealData ? footer.email : redacted
      }}</a>
      {{ footer.separator }}
      {{ useRealData ? footer.phone : redacted }}
    </p>
  </div>
</template>

<style scoped>
#ft {
  padding: 1em 0 1em 0;
  font-size: 92%;
  border-top: 1px solid #ccc;
  text-align: center;
}
#ft p {
  margin-bottom: 0;
  text-align: center;
}
</style>
