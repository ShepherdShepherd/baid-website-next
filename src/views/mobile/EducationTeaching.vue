<template>
  <div class="font-sans" :class="{'overflow-y-clip h-100vh':clip}">
    <Splash @clip="clip=false"/>
    <section class="p-3 snap-y snap-proximity overflow-y-scroll">
      <Curriculums class="snap-start"></Curriculums>
      <LearningMethod class="snap-start"></LearningMethod>
      <StudentGuidance class="snap-start"></StudentGuidance>
      <WonderfulMoment class="snap-start"></WonderfulMoment>
    </section>
  </div>
</template>

<script setup>
import Splash from '../../components/MobileEducationTeaching/EducationTeachingSplash.vue'
import Curriculums from '../../components/MobileEducationTeaching/CurriculumsIntroduction.vue'
import LearningMethod from '../../components/MobileEducationTeaching/LearningMethod.vue'
import StudentGuidance from '../../components/MobileEducationTeaching/StudentGuidance.vue'
import WonderfulMoment from '../../components/MobileEducationTeaching/WonderfulMoments.vue'

import { ref } from 'vue'
const clip = ref(true)
</script>
