<script setup>
import IconGitHub from "@/components/icons/IconGitHub.vue";
import IconLinkedIn from "@/components/icons/IconLinkedIn.vue";
import IconMail from "@/components/icons/IconMail.vue";
import IconCV from "@/components/icons/IconCV.vue";

const getPdfUrl = () => {
  return new URL(`../assets/conti-gianfranco-resume.pdf`, import.meta.url).href;
}
</script>

<template>
  <div class="bio-card">
    <h1>Conti Gianfranco</h1>
    <div class="bio-content">
      <img src="../assets/profile-square.png" alt="Profile Picture" class="profile-picture">
      <div class="bio-text">
        <p>
          Hi, I'm Gianfranco, a passionate software engineer based in Argentina.
        </p>
        <p>
          I am a master's student in computer engineering and am currently finishing my final thesis at UBA. With a strong passion for graphic programming and continuous learning, I love exploring new technologies and pushing the boundaries of what is possible in the digital world.
        </p>
      </div>
    </div>
    <div class="social-links">
      <a href="https://github.com/ContiGianfranco" class="link">
        <IconGitHub size=40 />
      </a>
      <a href="https://www.linkedin.com/in/gianfranco-conti-bb4b5828a/" class="link" >
        <IconLinkedIn size=40 />
      </a>
      <a href="mailto:giacocipo@gmail.com" class="link" >
        <IconMail size=40 />
      </a>
      <a :href="getPdfUrl()" target="_blank" class="link" id="resume-link">
        <IconCV size=40 />
      </a>
    </div>
  </div>
</template>

<style scoped>

@media (max-width: 550px) {
  .bio-content {
    display: flex;
    justify-content: space-around;
    align-items: center;
    flex-direction: column;
    padding: 2%;
  }

  .profile-picture {
    width: 150px;
    height: 150px;
    border-radius: 50%;
    margin-bottom: 5%;
  }

}

.link{
  margin-left: 3px;
}

.bio-card {
  padding: 2%;
  border-radius: 3px;
}

.bio-content {
  display: flex;
  justify-content: space-around;
  align-items: center;
  padding: 2%;
}

.bio-text {
  display: flex;
  flex-direction: column;
}

.profile-picture {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  margin-right: 5%;
}

.social-links {
  display: flex;
  flex-direction: row;
  justify-content: right;
}

.link {
  display: flex;
  justify-content: center;
}

</style>