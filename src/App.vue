<script setup>
import BioCard from "./components/BioCard.vue";
import ProjectsList from "@/components/ProjectsList.vue";
</script>

<template>
  <body>
    <BioCard />
    <ProjectsList />
    <footer class="footer">
      <p>Conti Gianfranco | &copy; 2024 All rights reserved.</p>
    </footer>
  </body>
</template>

<style scoped>
.footer {
  padding: 1rem;
  text-align: center;
}
</style>
