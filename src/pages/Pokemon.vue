<script>

import PokemonModal from '../components/PokemonModal.vue'
export default {
  components: {
    PokemonModal
  },
  data() {
    return {
      pokemonDeatil: {},
      isModalOpen: false,
      pokemon: [
        {
          imageUrl: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/1.svg",
          name: "balbusar",
          firstName: "grass",
          secondName: "poison",
        },
        {
          imageUrl: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/1.svg",
          name: "balbusar",
          firstName: "grass",
          secondName: "poison",
        },
        {
          imageUrl: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/1.svg",
          name: "balbusar",
          firstName: "grass",
          secondName: "poison",
        },
        {
          imageUrl: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/1.svg",
          name: "balbusar",
          firstName: "grass",
          secondName: "poison",
        },
        {
          imageUrl: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/1.svg",
          name: "balbusar",
          firstName: "grass",
          secondName: "poison",
        },
        {
          imageUrl: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/1.svg",
          name: "balbusar",
          firstName: "grass",
          secondName: "poison",
        },
        {
          imageUrl: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/1.svg",
          name: "balbusar",
          firstName: "grass",
          secondName: "poison",
        },
        {
          imageUrl: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/1.svg",
          name: "balbusar",
          firstName: "grass",
          secondName: "poison",
        },
        {
          imageUrl: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/1.svg",
          name: "balbusar",
          firstName: "grass",
          secondName: "poison",
        },
        {
          imageUrl: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/1.svg",
          name: "balbusar",
          firstName: "grass",
          secondName: "poison",
        },
        {
          imageUrl: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/1.svg",
          name: "balbusar",
          firstName: "grass",
          secondName: "poison",
        },
        {
          imageUrl: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/1.svg",
          name: "balbusar",
          firstName: "grass",
          secondName: "poison",
        },
        {
          imageUrl: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/1.svg",
          name: "balbusar",
          firstName: "grass",
          secondName: "poison",
        },
        {
          imageUrl: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/1.svg",
          name: "balbusar",
          firstName: "grass",
          secondName: "poison",
        },
        {
          imageUrl: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/1.svg",
          name: "balbusar",
          firstName: "grass",
          secondName: "poison",
        },
        {
          imageUrl: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/1.svg",
          name: "balbusar",
          firstName: "grass",
          secondName: "poison",
        },
        {
          imageUrl: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/1.svg",
          name: "balbusar",
          firstName: "grass",
          secondName: "poison",
        },
        {
          imageUrl: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/1.svg",
          name: "balbusar",
          firstName: "grass",
          secondName: "poison",
        },
        {
          imageUrl: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/1.svg",
          name: "balbusar",
          firstName: "grass",
          secondName: "poison",
        },
        {
          imageUrl: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/1.svg",
          name: "balbusar",
          firstName: "grass",
          secondName: "poison",
        },
      ]
    }
  },
  methods: {
    handleIsModalOpen(item) {
      this.pokemonDeatil = item
      this.isModalOpen = true
    }
  }
}
</script>

<template>
  <div>
    <div class="sm:mx-auto sm:container sm:my-24 my-5 sm:px-1 px-4">
      <h1 class="text-3xl font-medium text-blue-950">Pokedex</h1>
      <div class="mt-6 grid grid-cols-2 gap-2 sm:flex-wrap sm:gap-4 sm:flex sm:justify-center">
        <div class="bg-blue-950 shadow cursor-pointer sm:w-60 w-full rounded-lg sm:pt-16 pt-10 pb-6 px-2" @click="handleIsModalOpen(item)"
          v-for="item in (index, pokemon)">
          <img :src="item.imageUrl" alt="" class="w-20 mx-auto">
          <div>
            <h2 class="text-center pt-10 text-white">{{ item.name }}</h2>
            <div class="flex justify-center mt-5 gap-2">
              <h2 class="bg-blue-900 text-white rounded-full px-[12px] shadow py-[2px]">{{ item.firstName }}</h2>
              <h2 class="bg-blue-900 text-white rounded-full px-[12px] shadow py-[2px]">{{ item.secondName }}</h2>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div>
      <PokemonModal :isModalOpen="isModalOpen" @closeModal="isModalOpen = false" :pokemonDeatil="pokemonDeatil" />
    </div>
  </div>
</template>
