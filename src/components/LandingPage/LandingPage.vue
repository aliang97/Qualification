<script setup lang="ts">
import DescriptionText from './DescriptionText.vue';
import MainHeading from './MainHeading.vue';
import SocialLinks from './SocialLinks.vue';
import PhotoSrc from '@/assets/LandingPage/photo.jpg';
import GithubSVG from '@/assets/LandingPage/github.svg';
import LinkedinSVG from '@/assets/LandingPage/linkedin.svg';
import EmailSVG from '@/assets/LandingPage/email.svg';
import ResumeSVG from '@/assets/LandingPage/resume.svg';

const pageData = {
  photo: PhotoSrc,
  name: 'Alexander Liang',
  socials: [
    {
      href: 'https://github.com/aliang97',
      icon: GithubSVG,
      label: 'GitHub',
    },
    {
      href: 'https://www.linkedin.com/in/alex-liang-b1296230a/',
      icon: LinkedinSVG,
      label: 'LinkedIn',
    },
    {
      href: 'mailto:aliang97work@gmail.com',
      icon: EmailSVG,
      label: 'Email',
    },
    {
      href: 'https://drive.google.com/file/d/1FLwhDpweBLdqNl0v_PyLvmv_yoHUvxGK/view?usp=sharing',
      icon: ResumeSVG,
      label: 'Resume',
    },
  ],
  description: `Hello, I'm a full-stack software engineer looking for a job! I have 4+ years of experience with Javascript/Typescript, Python, and Go. I have worked both independently and as part of a larger team in an agile environment. I've also handled scoping discussions with clients as well and led some projects of my own.`,
};
</script>

<template>
  <div class="LandingPage background">
    <div class="container">
      <MainHeading :photo="pageData.photo" :heading="pageData.name" />
      <SocialLinks :socialData="pageData.socials" />
      <DescriptionText :textContent="pageData.description" />
    </div>
  </div>
</template>

<style scoped>
.LandingPage {
  min-height: calc(100vh - 200px);
  width: 100%;
  margin: 100px 0;
}

.background {
  background-color: var(--color-bg-1);
}

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>
