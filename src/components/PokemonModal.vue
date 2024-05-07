<template>
  <div>
    <transition name="modal-fade" appear>
      <div v-if="isModalOpen" class="fixed inset-0 z-50 flex items-center justify-end bg-black bg-opacity-50"
        @click="$emit('closeModal')">
        <div class="bg-blue-950 sm:max-w-[450px] w-full sm:ml-0 ml-10 h-full" @click.stop>
          <div class="h-[50%] px-5">
            <div class="flex items-center justify-between pt-10">
              <h2 class="text-white text-3xl font-medium">{{ pokemonDeatil.name }}</h2>
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
              <h1 class="flex justify-between mt-4 text-lg">
                <span class="text-blue-950 font-semibold">Experince:</span>
                <span class="text-blue-900 font-semibold">64 EX</span>
              </h1>
              <h1 class="flex justify-between mt-4 text-lg">
                <span class="text-blue-950 font-semibold">Hieght:</span>
                <span class="text-blue-900 font-semibold">7 m</span>
              </h1>
              <h1 class="flex justify-between mt-4 text-lg">
                <span class="text-blue-950 font-semibold">Weight:</span>
                <span class="text-blue-900 font-semibold">69 Kg</span>
              </h1>

            </div>
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
    return {};
  },
  methods: {},
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