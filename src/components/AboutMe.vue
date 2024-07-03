<template>
  <div class="container">
  <div class= "row">
    <h1 id="me">About Me</h1>

    <div v-if ="aboutMe">

<div class = "col">
<img src = "https://thuthuzaposwayo.github.io/All-images/images/girls.png"></div>


    <p> I am a young woman of colour that has taken on the journey to becoming one of the best front-end web developers in the industry.
        Despite the challenges of the tech industry, I am determined to make a success out my experience at Life Choices as a Web Developments student.
        I have gained the fundamental skills and experince in HTML, CSS and JavaScript and I am looking forward to learning much more!
        The technology industry has grown tremendously, and continues to do so. I am determined to consisently evolve and strengthen my skills. 
        My passion and daring personality makes me stand out! 

    </p>
</div>
    <Spinner v-else />
  </div>
    </div>
</template>

<script setup>
import Spinner from "./Spinner.vue";
import { computed, onMounted} from "vue";
import { useStore } from "veux";

const store = useStore();
const aboutMe = computed(()  => store.state.about);

onMounted(()  => {
    store.dipatch("fetchAbout")
})

</script>

<style>

</style>