<template>
  <div class="container">
  <div class= "row">
    <h1 id="me">About Me</h1>

    <div v-if ="about">
        <span>{{ about }}</span>




   
</div>
    <Spinner v-else />
    <div class = "
    justify-content-center">
        <img src = "https://thuthuzaposwayo.github.io/All-images/images/girls.png"   id="tech"></div>
  </div>
    </div>
</template>

<script setup>
import Spinner from "./Spinner.vue";
import { computed, onMounted} from "vue";
import { useStore } from "vuex";

const store = useStore();
const about = computed(()  => store.state.about);

onMounted(()  => {
    store.dispatch("fetchAbout")
})

</script>

<style scoped>
span{
    font-family: Playfair Display;
    color: rgb(252, 247, 241);
    margin-bottom: 100px;

   

}
#me{
    font-family: Playfair Display;
    margin-top: 50px;
    margin-bottom: 50px;
    font-weight: bold;
}

.container{
    border: 5px solid bisque;
    border-radius: 4rem;
    padding: 50px;
    margin-top: 100px;
    margin-bottom: 100px;
}
</style>