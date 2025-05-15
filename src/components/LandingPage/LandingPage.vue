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

const buttonClick = () => {
  const sectionElement = document.querySelector('.AboutMe');
  if (!sectionElement) {
    return;
  }

  const sectionTopCoord = sectionElement.getBoundingClientRect().top + window.scrollY;
  window.scrollTo({ top: sectionTopCoord, behavior: 'smooth' });
};
</script>

<template>
  <div class="LandingPage background">
    <div class="container">
      <MainHeading :photo="pageData.photo" :heading="pageData.name" />
      <SocialLinks :socialData="pageData.socials" />
      <DescriptionText :textContent="pageData.description" />
    </div>
    <div class="downButtonContainer">
      <button class="downButton" v-on:click="buttonClick">
        <svg fill="#f2f2f2" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
          <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
          <g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g>
          <g id="SVGRepo_iconCarrier">
            <path
              d="M11.178 19.569a.998.998 0 0 0 1.644 0l9-13A.999.999 0 0 0 21 5H3a1.002 1.002 0 0 0-.822 1.569l9 13z"
            ></path>
          </g>
        </svg>
      </button>
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
  position: relative;

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

.downButtonContainer {
  position: absolute;
  bottom: -40px;
  left: 50%;
  transform: translate(-50%, -50%);
}

.downButton {
  height: 40px;
  width: 40px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: background-color 0.2s ease;
}

.downButton:hover {
  background-color: var(--color-text-1);
  cursor: pointer;
}

svg {
  height: 20px;
  width: 20px;
  transition: fill 0.2s ease;
}

.downButton:hover svg {
  fill: var(--color-bg-1);
}
</style>
