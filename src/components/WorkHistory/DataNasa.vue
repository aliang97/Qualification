<script setup lang="ts">
import CompanyHeading from './CompanyHeading.vue';
import NASALogo from '@/assets/WorkHistory/nasa.png';

const companyHeadingData = {
  logoSrc: NASALogo,
  name: 'NASA Langley Research Center',
  tenure: '2016 - 2017',
  title: 'Intern',
};
</script>

<template>
  <div class="DataNasa">
    <CompanyHeading v-bind="companyHeadingData" />
    <ul>
      <li>
        Gathered psychophysiological data from pilots in flight simulators being subjected to
        hypoxic conditions to measure their ability to make quick and accurate decisions.
      </li>
      <li>
        Trained a machine learning classifier to identify if a pilot's condition was impaired due to
        hypoxia.
      </li>
    </ul>
  </div>
</template>

<style scoped>
.DataNasa {
  font-size: 16px;
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
