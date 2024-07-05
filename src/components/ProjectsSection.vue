<template>
  <div class="container">
    <div class="row gap-4 justify-content-around" v-if="projects?.length">
      <h1 class="display-4">Projects</h1>
      <Card v-for="(project, index) in projects" :key="index" class="card">
        <template #cardHeader>
          <img :src="project.image" alt="" class="img-fluid">
          <h4>{{project.project}}</h4>
          <p class="text-capitalize">{{project.role}}</p>
          <p>{{project.testimonial}}</p>
          <a class="btn btn-primary me-2" :href="project.vercel-link">Vercel <i class="bi bi-globe"></i></a>
          <a class="btn btn-primary" :href="project.github-link">Github <i class="bi bi-github"></i></a>
        </template>
      </Card>
    </div>
    <Spinner v-else />
  </div>
</template>
<script setup>
import Spinner from "./Spinner.vue";
import Card from "@/components/Card.vue";

import { computed, onMounted } from "vue";
import { useStore } from "vuex";

const store = useStore();
const projects = computed(() => store.state.projects);
onMounted(() => {
  store.dispatch("fetchProjects");
});
</script>

<style scoped>
.display-4{
  font-family: Playfair Display;

}

</style>











<!-- <template>
  <div>
    <div class="row gap-4" v-if="projects?.length">
      <CardComp v-for="(project, index) in projects" :key="index">
        <template #cardHeader>
          
        </template>
      </CardComp>
    </div>
    <Spinner v-else />
  </div>
</template>

<script>
import CardComp from "@/components/Card.vue";
import Spinner from "@/components/Spinner.vue"
import { mapActions, mapState } from "vuex";

export default {
  components: {
    CardComp,
    Spinner
  },
  methods: {
    ...mapActions(['fetchProjects'])
  },
  computed: {
    ...mapState(['projects'])
  }-->

