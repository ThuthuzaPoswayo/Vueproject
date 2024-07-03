<template>
  <div class="container">
    <div class="row">
    
      
    
   <section class="row" id="landing">
  <LandingPage />
   </section>
   <section class="row" id="about">
    <AboutMe />

   </section>
   <section class="row" id="resume">

   </section>
   <section class="row" id="project">

   </section>
   <section class="row" id="testimonials">

   </section>
   <section class="row" id="reach me">
    
   </section>
  </div>
</div>
</template>

<script>
import LandingPage from '@/components/LandingPage.vue'
import AboutMe from '@/components/AboutMe.vue'

export default {
  name: 'HomeView',
  components: {
    LandingPage,
    AboutMe,
  }
}


</script>
