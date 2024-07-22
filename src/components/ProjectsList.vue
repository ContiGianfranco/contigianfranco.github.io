<script setup>
  import ProjectsData from '@/assets/jsons/projects.json';
  import IconGitHub from "@/components/icons/IconGitHub.vue";
  defineProps(ProjectsData);

  const redirectTo = (url) => {
    window.location.href = url;
  };

  const getImageUrl = (name) => {
    return new URL(`/src/assets/screenshots/${name}.jpg`, import.meta.url).href;
  }
</script>

<template>
  <ul class="cards" v-for="project in ProjectsData.projects">
    <li @click="redirectTo(project.demo)" class="card">
      <div class="card-info">
        <div>
          <h2 class="project-name">{{project.name}}</h2>
          <h3 class="project-description">{{project.description}}</h3>
        </div>
        <div class="repo-link">
          <a :href="project.repo" class="project-link">
            <IconGitHub size=40 />
          </a>
        </div>
      </div>
      <div class="image-container">
        <div class="image-gradient"></div>
        <img :src="getImageUrl(project.image)" alt="Project image" class="projects-image">
      </div>
    </li>
  </ul>
</template>

<style scoped>

.project-link{
  display: flex;
  justify-content: center;
}

.repo-link{
  display: flex;
  justify-content: right;
  align-self: flex-end;
}

.cards {
  padding: 0;
  display: flex;
  flex-direction: column;
  list-style-type: none;
}

.card {
  display: flex;
  justify-content: space-between;
  flex-direction: row;
  border-radius: 3px;
  margin-top: 20px;
}

.card-info{
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin: 2%;
  width: 50%;
}

.image-container {
  width: 50%;
  height: auto;
  position: relative;
  border-radius: 3px;
}

.projects-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: inline-block;
  border-radius: 3px;
}

.image-gradient {
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  left: 0;
}

@media (max-width: 550px) {
  .card-info{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    margin: 2%;
    width: 70%;
  }

  .image-container {
    width: 30%;
    height: auto;
    position: relative;
    border-radius: 3px;
  }

  .project-name {
    font-size: 20px;
  }

  .project-description {
    font-size: 16px;
  }
}

</style>