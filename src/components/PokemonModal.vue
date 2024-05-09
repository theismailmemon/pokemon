<template>
  <div>
    <transition name="modal-fade" appear>
      <div v-if="isModalOpen" class="fixed inset-0 z-50 flex items-center justify-end bg-black bg-opacity-50"
        @click="$emit('closeModal')" @touchstart="handleTouchStart" @touchmove="handleTouchMove"
        @touchend="handleTouchEnd">
        <div class="bg-blue-950 sm:max-w-[450px] w-full sm:ml-0 ml-12 h-full" @click.stop>
          <div class="h-[50%] px-5">
            <div class="flex items-center justify-between pt-10">
              <h2 class="text-white sm:text-3xl text-[26px] font-medium">{{ pokemonDeatil.name }}</h2>
              <h2 class="text-white"># <span v-if="pokemonDeatil.id <= 9">0</span><span>{{ pokemonDeatil.id }}</span>
              </h2>
            </div>
            <div class="flex justify-start mt-5 gap-2">
              <h2 class="bg-blue-900 text-white rounded-full px-[12px] shadow py-[2px]">{{ pokemonDeatil.firstName }}
              </h2>
              <h2 class="bg-blue-900 text-white rounded-full px-[12px] shadow py-[2px]">{{ pokemonDeatil.secondName }}
              </h2>
            </div>
            <div class="flex items-center h-[calc(100%-120px)]">
              <img :src="pokemonDeatil.imageUrl" alt="" class="w-40 mx-auto">
            </div>
          </div>
          <div class="bg-white rounded-t-3xl h-[50%] px-5 pt-10">
            <div class="max-w-48">
              <h1 class="flex justify-between sm:mt-4 mt-3 text-[17px] sm:text-lg">
                <span class="text-blue-950 font-semibold">Experience:</span>
                <span class="text-blue-900 font-semibold">64 EXP</span>
              </h1>
              <h1 class="flex justify-between sm:mt-4 mt-3 text-[17px] sm:text-lg">
                <span class="text-blue-950 font-semibold">Height:</span>
                <span class="text-blue-900 font-semibold">7 m</span>
              </h1>
              <h1 class="flex justify-between sm:mt-4 mt-3 text-[17px] sm:text-lg">
                <span class="text-blue-950 font-semibold">Weight:</span>
                <span class="text-blue-900 font-semibold">69 Kg</span>
              </h1>
            </div>
          </div>
        </div>
        <div v-if="showSwipeIndicator" class="absolute top-0 left-0 flex items-center h-full text-white">
          <div class="w-12 h-full flex items-center justify-center bg-blue-900">
            <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-arrow-right" width="24"
              height="24" viewBox="0 0 24 24" stroke-width="1.5" stroke="#ffffff" fill="none" stroke-linecap="round"
              stroke-linejoin="round">
              <path stroke="none" d="M0 0h24v24H0z" fill="none" />
              <path d="M5 12l14 0" />
              <path d="M13 18l6 -6" />
              <path d="M13 6l6 6" />
            </svg>
          </div>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  props: {
    pokemonDeatil: Object,
    isModalOpen: Boolean,
  },
  data() {
    return {
      touchStartX: 0,
      showSwipeIndicator: false,
    };
  },
  methods: {
    handleTouchStart(event) {
      this.touchStartX = event.touches[0].clientX;
      this.showSwipeIndicator = true; // Show swipe indicator when touch starts
    },
    handleTouchMove(event) {
      const touchMoveX = event.touches[0].clientX;
      if (touchMoveX - this.touchStartX > 50) {
        // If sliding right, hide swipe indicator
        this.showSwipeIndicator = false;
      }
    },
    handleTouchEnd(event) {
      const touchEndX = event.changedTouches[0].clientX;
      if (touchEndX - this.touchStartX > 50) {
        // If the touch ended with a left swipe (positive difference in X coordinates)
        this.$emit('closeModal');
      }
      this.showSwipeIndicator = false; // Hide swipe indicator when touch ends
    },
  },
};
</script>

<style scoped>
.modal-fade-enter-active,
.modal-fade-leave-active {
  transition: opacity 0.2s;
}

.modal-fade-enter,
.modal-fade-leave-to {
  opacity: 0;
}
</style>
