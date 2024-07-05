<template>
<div v-if="education">
  <div class="container-fluid">
    <div class="row gap-5 justify-content-center mt-5">
      <h1 class="fw-bold mb-5">Education</h1>
      <div v-for="(edu, index) in education" :key="index">
        <div class="card" style="width: 18rem">
          <img :src="edu.image" class="card-img-top" />
          <div class="card-body">
            <h5 class="card-title">{{ edu.institution }}</h5>
            <p class="card-text">{{ edu.qualification }}</p>
            <p class="card-text">{{ edu.year }}</p>
          </div>
        </div>
      </div>
    </div>
    <div class="row">

      <h3 class="details">Skills</h3>
      <ul>
      <li>
        <strong>{{ skills[0].skillName1 }}<i class="bi bi-filetype-html"></i></strong>
      </li>
      <li>
        <strong>{{ skills[0].skillName2 }}</strong>
      </li>
      <li>
        <strong>{{ skills[0].skillName3 }}</strong>
      </li>
      <li>
        <strong>{{ skills[0].skillName }}</strong>
      </li>
    </ul>
    </div>
    <div v-if="experience" class="experience row">
      <h3>Experience</h3>

      <li v-for="exp in experience" :key="exp.id">
        <p>{{ exp.jobTitle }}</p>
        <p>{{ exp.year }}</p>
        <p>{{ exp.description }}</p>
      </li>
    </div>
  </div>
</div>
  <Spinner v-else />
</template>
<script setup>
import Spinner from "@/components/Spinner.vue";
import { computed, onMounted } from "vue";
import { useStore } from "vuex";

const store = useStore();
const education = computed(() => store.state.education);
const skills = computed(() => store.state.skills);
const experience = computed(() => store.state.experience);

onMounted(() => {
  store.dispatch("fetchEducation");
  store.dispatch("fetchSkills");
  store.dispatch("fetchExperience");
});
</script>

<style scoped>
#resume {
  font-family: Playfair Display;
  color: rgb(252, 247, 241);
  margin-bottom: 100px;
}
.resume-section {
  font-family: Arial, sans-serif;
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
  background-color: #f0f0f0;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}
.row{
  font-family: Playfair Display;
}
.skills strong {
  margin-right: 10px;
  color: #007bff;
}
li {
  list-style: none;
}
</style>
