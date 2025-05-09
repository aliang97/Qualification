<script setup lang="ts">
import CompanyHeading from './CompanyHeading.vue';
import YextSVG from '@/assets/WorkHistory/YextLogo.svg';

const companyHeadingData = {
  logoSrc: YextSVG,
  name: 'SimonComputing',
  tenure: '2017 - 2018',
  title: 'Intern',
};
</script>

<template>
  <div class="DataSimonComputing">
    <CompanyHeading v-bind="companyHeadingData" />
    <ul>
      <li>
        Created a React UI for internal use which tracked the company’s in-flight projects and
        contracts.
      </li>
      <li>
        Gathered feedback and suggestions from other employees. Prioritized bug fixes and feature
        requests based on estimated difficulty and user impact.
      </li>
    </ul>
  </div>
</template>

<style scoped>
.DataSimonComputing {
  font-size: 16px;
  margin-bottom: 16px;
}

ul {
  margin-left: 32px;
}

li {
  list-style-type: disc;
  list-style-position: outside;
  margin: 4px 0;
}
</style>
