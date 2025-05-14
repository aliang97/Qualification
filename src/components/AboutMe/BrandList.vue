<script setup lang="ts">
import HTMLSrc from '@/assets/AboutMe/logos/html5.png';
import CSSSrc from '@/assets/AboutMe/logos/css.png';
import JSSrc from '@/assets/AboutMe/logos/js.png';
import TSSrc from '@/assets/AboutMe/logos/ts.png';
import ReactSrc from '@/assets/AboutMe/logos/react.png';
import VueSrc from '@/assets/AboutMe/logos/vue.png';
import PythonSrc from '@/assets/AboutMe/logos/python.png';
import GoSrc from '@/assets/AboutMe/logos/go.png';
import WebpackSrc from '@/assets/AboutMe/logos/webpack.webp';
import ViteSrc from '@/assets/AboutMe/logos/vite.png';
import SassSrc from '@/assets/AboutMe/logos/sass.jpg';
import BootstrapSrc from '@/assets/AboutMe/logos/bootstrap.png';
import JquerySrc from '@/assets/AboutMe/logos/jquery.png';
import AngularSrc from '@/assets/AboutMe/logos/angular.png';
import HandlebarsSrc from '@/assets/AboutMe/logos/handlebars.webp';
import GruntSrc from '@/assets/AboutMe/logos/grunt.png';
import JenkinsSrc from '@/assets/AboutMe/logos/jenkins.png';
import MysqlSrc from '@/assets/AboutMe/logos/mysql.png';
import I18nextSrc from '@/assets/AboutMe/logos/i18next.png';
import TailwindSrc from '@/assets/AboutMe/logos/tailwind.png';
import HexagonComponent from './HexagonComponent.vue';

const content = [
  {
    label: 'HTML5',
    imageSrc: HTMLSrc,
  },
  {
    label: 'CSS3',
    imageSrc: CSSSrc,
  },
  {
    label: 'Javascript',
    imageSrc: JSSrc,
  },
  {
    label: 'Typescript',
    imageSrc: TSSrc,
  },
  {
    label: 'React',
    imageSrc: ReactSrc,
  },
  {
    label: 'Vue',
    imageSrc: VueSrc,
  },
  {
    label: 'Python',
    imageSrc: PythonSrc,
  },
  {
    label: 'Go',
    imageSrc: GoSrc,
  },
  {
    label: 'Webpack',
    imageSrc: WebpackSrc,
  },
  {
    label: 'Vite',
    imageSrc: ViteSrc,
  },
  {
    label: 'Sass',
    imageSrc: SassSrc,
  },
  {
    label: 'Bootstrap',
    imageSrc: BootstrapSrc,
  },
  {
    label: 'Jquery',
    imageSrc: JquerySrc,
  },
  {
    label: 'Tailwind',
    imageSrc: TailwindSrc,
  },
  {
    label: 'I18next',
    imageSrc: I18nextSrc,
  },
  {
    label: 'Angular',
    imageSrc: AngularSrc,
  },
  {
    label: 'Handlebars',
    imageSrc: HandlebarsSrc,
  },
  {
    label: 'Grunt',
    imageSrc: GruntSrc,
  },
  {
    label: 'Jenkins',
    imageSrc: JenkinsSrc,
  },
  {
    label: 'Mysql',
    imageSrc: MysqlSrc,
  },
];
</script>

<template>
  <div class="BrandList container">
    <ul>
      <li v-for="item in content" :key="item.label" class="hexagonWrapper">
        <HexagonComponent v-bind="item" />
      </li>
    </ul>
  </div>
</template>

<style scoped>
.BrandList {
  width: 100%;
  padding: 0;
  padding-top: 16px;

  @media (max-width: 769px) {
    display: none;
  }
}

ul {
  display: flex;
  flex-wrap: wrap;
  padding: 0 32px;
  padding-top: 52px;
}

.hexagonWrapper {
  width: 92px;
  height: 100px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 4px 0;
}

.hexagonWrapper:nth-child(even) {
  position: relative;
  top: -54px;
}
</style>
