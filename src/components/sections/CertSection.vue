<script setup lang="ts">
import Section from "../templates/ContentTemplate.vue";
import FigureItem from "../templates/FigureItem.vue";
import Terraform002CertImage from "@/assets/hashicorp-certified-terraform-associate-002.png";
import AzFundamentalsCertImage from "@/assets/microsoft-certified-azure-fundamentals.png";

class Cert {
  url: string;
  name: string;
  period: string;

  constructor(url: string, name: string, period: string) {
    this.url = url;
    this.name = name;
    this.period = period;
  }
}

class ImageCert extends Cert {
  image: string;

  constructor(cert: Cert, image: string) {
    super(cert.url, cert.name, cert.period);
    this.image = new URL(image, import.meta.url).href;
  }
}

const azCert = new Cert(
  "https://www.credly.com/badges/1de277ca-e830-4274-88ff-0a341fc4d915/embedded",
  "Azure Fundamentals",
  "Nov 2022"
);

const azCertEmbedded = new ImageCert(azCert, AzFundamentalsCertImage);

const tfCert = new Cert(
  "https://www.credly.com/badges/56181ee1-239c-430f-88ae-d1a3ddf872ae/public_url",
  "Terraform Associate",
  "Feb 2023"
);
const tfCertEmbedded = new ImageCert(tfCert, Terraform002CertImage);
</script>

<template>
  <Section>
    <template #heading>Certifications</template>
    <div class="wrapper">
      <FigureItem>
        <template #image>
          <a :href="azCert.url">
            <img :src="azCertEmbedded.image" :alt="azCertEmbedded.name" />
          </a>
        </template>
        <template #caption> {{ azCert.period }}</template>
      </FigureItem>
      <FigureItem>
        <template #image>
          <a :href="tfCert.url">
            <img :src="tfCertEmbedded.image" :alt="tfCertEmbedded.name" />
          </a>
        </template>
        <template #caption> {{ tfCert.period }}</template>
      </FigureItem>
    </div>
  </Section>
</template>

<style scoped>
img {
  max-height: 123px;
  max-width: 123px;
}
/* Display certs in rows, spaced evenly */
.wrapper {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  text-align: center;
  justify-content: space-around;
}

</style>
