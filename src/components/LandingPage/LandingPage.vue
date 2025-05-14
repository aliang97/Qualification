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
      href: 'https://aliang97.github.io/Resume/Resume.pdf',
      icon: ResumeSVG,
      label: 'Resume',
    },
  ],
  description: `Hi, I'm a full-stack software engineer looking for work! I have 5+ years of experience with Javascript/Typescript, Python, and Go.`,
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
  --color-bg-1: var(--color-black-1);
  --color-text-1: var(--color-white-1);

  min-height: calc(100vh - 200px);
  width: 100%;
  margin: 100px 0;

  @media (max-width: 426px) {
    margin: 32px 0;
  }
}

.background {
  background-color: var(--color-bg-1);
  color: var(--color-text-1);
}

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>
