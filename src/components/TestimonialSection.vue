<template>
  <div class="container">
    <div class="row gap-4 justify-content-around" v-if="testimonials?.length">
      <h1 class="display-1">Testimonials</h1>
      <Card v-for="(testimony, index) in testimonials" :key="index" class="card">
        <template #cardHeader>
          <img :src="testimony.image" alt="" class="img-fluid">
          <h4>{{testimony.name}}</h4>
          <p class="text-capitalize">{{testimony.role}}</p>
          <p>{{testimony.testimonial}}</p>
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
const testimonials = computed(() => store.state.testimonials);
onMounted(() => {
  store.dispatch("fetchTestimonials");
});
</script>

