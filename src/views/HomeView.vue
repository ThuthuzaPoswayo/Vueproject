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
  <ResumeSection />
   </section>

   <section class="row" id="projects">
  </section>
   
  <section class="row" id="testimonials">

   </section>
   <section class="row" id="reach me">
    
   </section>

  
    <!-- <section class= "row" id="education">
      <ResumeSection />
    </section>
   
    <section class =row id="experience">
      <ResumeSection/>
    </section> -->
  </div>
</div>
</template>

<script>
import LandingPage from '@/components/LandingPage.vue'
import AboutMe from '@/components/AboutMe.vue'
import ResumeSection from '@/components/ResumeSection.vue'
export default {
  name: 'HomeView',
  components: {
    LandingPage,
    AboutMe,
    ResumeSection
  }
}


</script>
