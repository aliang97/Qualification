<script setup lang="ts">
import PhotoSrc from '@/assets/AboutMe/photo_cropped.png';
</script>

<template>
  <div class="MainContent">
    <div class="photo">
      <img :src="PhotoSrc" alt="" />
    </div>
    <div class="textContent">
      <ul>
        <li>University of Virginia 2019 Graduate - BS in Computer Science - GPA 3.9.</li>
        <li>
          5+ years of professional experience working with Javascript/Typescript, Python, and Go.
        </li>
        <li>
          Extensive knowledge of front-end web dev, including low level HTML/CSS, high level
          frameworks like ReactJS and VueJS, and bundling/transpiling packages like Webpack or Vite.
        </li>
        <li>
          Experience with setting up and maintaining backend API endpoints to ingest data or expose
          data for consumption.
        </li>
        <li>
          Worked both as an independent developer and as part of a team in an Agile environment.
        </li>
        <li>
          Played many roles in a team, including public-facing roles like establishing deliverables
          with clients and managing feedback/modifications, and internal roles like scoping/breaking
          down projects, assigning tasks to other team members, and prioritizing tasks.
        </li>
      </ul>
    </div>
  </div>
</template>

<style scoped>
.MainContent {
  display: flex;
  flex-direction: row;
  gap: 32px;

  @media (max-width: 769px) {
    flex-direction: column;
  }
}

.photo {
  margin: auto;
}

img {
  width: 285px;
  height: 300px;
  border-radius: 8px;

  @media (max-width: 769px) {
    width: 100%;
    max-width: 350px;
    height: unset;
  }
}

.textContent {
  font-size: 16px;
  line-height: 1.6;
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
