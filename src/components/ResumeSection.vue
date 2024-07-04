<template>
  <div class="container">
    <div class="row">
      <div id="resume">
        <h1 class="display-1">Resume</h1>

        <!--Education Section-->
        <div>
          <h3 class="display-2">Education</h3>
          <div class="row gap-4" v-if="education">
            <CardComp v-for="(educ, id) in education" :key="id">
              <template #cardHeader>
                <h3 class="heading">{{ edueduccation.institution }}</h3>
                <!-- <img src="" alt="academy-img"/> -->
              </template></CardComp
            >
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<template #cardBody>
  <p>{{ educ.qualification }}</p>
  <p>{{ educ.year }}</p>
</template>
</CardComp>
</div>
<Spinner  v-else />
</div>

<!-- Skills -->

<div>
  <h3 class="display-2">Skills</h3>
  <div class ="row gap-4" v-if="skills?.length">
   
<CardComp v-for="item in skills"   :key="item.id">
  <template>
  <img src="" alt="academy-img" />
</template>
<template>
  <p class="heading">{{ item.skillName1 }}</p>
  <p>{{ item.skillName2 }}</p>
  <p>{{ item.skillName }}</p>
</template>
</CardComp>
</div>
<Spinner  v-else />
</div>


<!-- Experience -->
<div>
  <h3 class="display-2">Experience</h3>
  <div class ="row gap-4" v-if="experience?.length">
   
<CardComp v-for="item in experience"   :key="item.id">
  <template>
  <img src="" alt="academy-img" />
</template>
<template>
  <p class="heading">{{ item.jobTitle }}</p>
  <p>{{ item.year }}</p>
  <p>{{ item.description }}</p>
</template>
</CardComp>
</div>
<Spinner  v-else />
</div>



    </div>
   </div>
  </div>
</template>









<script setup>
import Spinner from "./Spinner.vue";
import { computed, onMounted } from "vue";
import { useStore } from "vuex";

const store = useStore();
const education = computed(() => store.state.education);
const skills = computed(() => store.state.skills);
const experience = computed(() => store.state.experience);

onMounted(() => {
  store.dispatch("fetchEducation");
  store.dispatch("fetchSkills");
  store.dispatch("fetchexperience");
});
</script>

<style>
</style>