<template>
  <div
    id="container"
    class="my-10 py-5 flex flex-col justify-center items-center"
  >
    <h1 class="text-10 font-300 font-title color-white text-center">
      {{ $t('StudentLife.Clubs.Title') }}
    </h1>
    <div class="flex justify-center items-center w-274">
      <DesktopSwiper slides="4">
        <swiper-slide
          v-for="club in clubs"
          :key="club"
          @click="
            ;(clubName = $t(club.name)),
              (clubDescription = $t(club.description)),
              (clubImgs = club.images),
              (showInfo = true)
          "
          class="flex justify-center py-3"
        >
          <div
            class="h-220px aspect-1 items-center justify-center flex flex-col"
            style="box-shadow: 8px 4px 4px 3px rgba(0, 0, 0, 0.5)"
            :style="{ 'background-color': club.bgColor, color: club.color }"
          >
            <div class="text-8 font-title m-1">
              {{ $t(club.name) }}
            </div>
            <div class="m-1">
              <img
                :src="club.logo"
                class="w-80px aspect-1 object-cover block"
              />
            </div>
          </div>
        </swiper-slide>
      </DesktopSwiper>
      <Transition>
        <ClubInfo
          v-if="showInfo"
          @close="showInfo = false"
          :name="clubName"
          :description="clubDescription"
          :images="clubImgs"
        ></ClubInfo
      ></Transition>
    </div>
  </div>
</template>

<script setup>
import ClubInfo from './ClubInfo.vue'
import DesktopSwiper from '../DesktopSwiper.vue'
import { ref } from 'vue'
import { SwiperSlide } from 'swiper/vue'
import { clubs } from '../../data/Clubs.js'

const showInfo = ref(false)
const clubName = ref(null)
const clubDescription = ref(null)
const clubImgs = ref(null)
</script>

<style scoped>
#container {
  background-image: url('../../assets/images/campusBg3.png?webp');
  background-repeat: no-repeat;
  background-size: 100% 600px;
}
.v-enter-active {
  transition-property: all;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 200ms;
}

.v-leave-active {
  transition-property: all;
  transition-timing-function: cubic-bezier(0, 0, 0.2, 1);
  transition-duration: 150ms;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>
