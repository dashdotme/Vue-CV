<script setup lang="ts">
import Intro from "./sections/IntroSection.vue";
import Foot from "./sections/FooterSection.vue";
import JobSection from "./sections/JobSection.vue";
import TechnicalSection from "./sections/TechnicalSection.vue";
import CertSection from "./sections/CertSection.vue";
import AboutSection from "./sections/AboutSection.vue";
import EducationSection from "./sections/EducationSection.vue";
import TestimonialsSection from "./sections/TestimonialsSection.vue";
import ReferencesSection from "./sections/ReferencesSection.vue";

// placeholder
const useRealData = false;
// TODO: can encrypt contact data instead. Easier to maintain.

</script>
<template>
  <body>
    <div id="doc2">
      <div id="inner">
        <Intro  :use-real-data="useRealData" />
        <body>
          <JobSection />
          <TechnicalSection />
          <CertSection />
          <AboutSection />
          <EducationSection />
          <TestimonialsSection :use-real-data="useRealData"/>
          <ReferencesSection :use-real-data="useRealData"/>
        </body>
        <Foot :use-real-data="useRealData"/>
      </div>
    </div>
  </body>
</template>

<style>
@import "../assets/reset-fonts-grids.css";

body {
  font-family: Georgia;
  color: #444;
  font-weight: normal;
}

#docbox {
  width: 73em;
  margin: auto;
  text-align: left;
}

#inner {
  padding: 10px 80px;
  margin: 80px auto;
  background: #f5f5f5;
  border: solid #666;
  border-width: 8px 0 2px 0;
}

.section {
  margin-bottom: 2em;
  padding-bottom: 2em;
  border-bottom: 1px solid #ccc;
}

#bd,
#ft {
  margin-bottom: 2em;
}

#hd h1 {
  font-size: 48px;
  text-transform: uppercase;
  letter-spacing: 3px;
}
h2 {
  font-size: 152%;
}
h3,
h4 {
  font-size: 122%;
}
h1,
h2,
h3,
h4 {
  color: #333;
}
p {
  font-size: 100%;
  line-height: 18px;
  padding-right: 3em;
}
a {
  color: #990003;
}
a:hover {
  text-decoration: none;
}
strong {
  font-weight: bold;
}
li {
  line-height: 16px;
  border-bottom: 1px solid #ccc;
}
p.enlarge {
  font-size: 144%;
  padding-right: 6.5em;
  line-height: 24px;
}
p.enlarge span {
  color: #000;
}
.contact-info {
  margin-top: 7px;
  text-align: center;
}
.first h2 {
  font-style: italic;
}
</style>
