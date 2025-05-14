<script setup lang="ts">
import CompanyHeading from './CompanyHeading.vue';
import YextSVG from '@/assets/WorkHistory/YextLogo.svg';

const companyHeadingData = {
  logoSrc: YextSVG,
  name: 'Yext',
  tenure: '2019 - 2024',
  title: 'Software Engineer II - Software Engineer IV',
};
</script>

<template>
  <div class="DataYext">
    <CompanyHeading v-bind="companyHeadingData" />
    <ul>
      <li>
        Built customized landing pages, store locators, and directories for clients using Closure
        Templates or React with a focus on search engine optimization, responsive design, and user
        activity analytics tracking. For some examples of my work, you can visit these live pages:
        <ul>
          <li>
            <a href="https://locations.outback.com">https://locations.outback.com</a> (100k average
            daily pageviews)
          </li>
          <li>
            <a href="https://storelocator.asda.com">https://storelocator.asda.com</a> (50k average
            daily pageviews)
          </li>
          <li>
            <a href="https://bankers.amerisbank.com">https://bankers.amerisbank.com</a> (10k average
            daily pageviews)
          </li>
        </ul>
      </li>
      <li>
        Implemented Extract-Transform-Load (ETL) routines to automatically pull data from client API
        endpoints into the Yext platform using Golang with a focus on test-coverage and error
        reporting.
      </li>
      <li>
        Improved team efficiency by updating internal tooling - refactored webpack config & plugins
        to upgrade from v3 to v4, developed reusable components for the Yext component library, etc.
      </li>
      <li>
        Directed a modernization effort to switch from Closure Templates to React. Replicated the
        Yext component library in React. Set up a Yext react starter app to quickly spin up new
        projects.
      </li>
      <li>
        Added multi-language support with react-i18next to the Yext react starter app. Wrote scripts
        to automatically generate and sync .po files with the Yext Smartling account.
      </li>
      <li>
        Established procedures & criteria for upgrading existing pages from Closure Templates to
        React. Wrote and maintained documentation describing how various features should be
        upgraded.
      </li>
      <li>
        Led the React Rebuild team to upgrade existing pages from Closure Templates to React.
        Communicated with stakeholders about timelines, broke down projects, and assigned work.
      </li>
      <li>
        Mentored and trained engineers who joined the React Rebuild team. Provided feedback and made
        suggestions to engineers via pull requests and pair programming.
      </li>
    </ul>
  </div>
</template>

<style scoped>
.DataYext {
  font-size: 16px;
  margin-bottom: 16px;
}

ul {
  margin-left: 32px;

  @media (max-width: 426px) {
    margin-left: 24px;
  }
}

li {
  list-style-type: disc;
  list-style-position: outside;
  margin: 4px 0;
}
</style>
