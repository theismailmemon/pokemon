<script>

import Pokemon from './pages/Pokemon.vue'
export default {
  components: {
    Pokemon
  },
  data() {
    return {

    }
  },
  mounted() {
        this.$nextTick(() => {
            this.setScrollbarHeight();
            window.addEventListener('resize', this.setScrollbarHeight);
        });
    },
    beforeDestroy() {
        window.removeEventListener('resize', this.setScrollbarHeight);
    },
  methods: {
    setScrollbarHeight() {
            const customScrollbar = this.$refs.customScrollbar;
            customScrollbar.style.maxHeight = '100vh'; // Set max-height to 100% of viewport height
        }
  }
}
</script>

<template>
  <section ref="customScrollbar" class="custom-scrollbar">
    <Pokemon />
  </section>
</template>

<style scoped>
/* Scoped styles to apply scrollbar to the content inside the modal */
.custom-scrollbar {
    overflow-y: auto;
}

.custom-scrollbar::-webkit-scrollbar {
    width: 10px;
}

.custom-scrollbar::-webkit-scrollbar-track {
    background: #f1f1f1;
}

.custom-scrollbar::-webkit-scrollbar-thumb {
    background: #3b82f6;
    border-radius: 5px;
}

.custom-scrollbar::-webkit-scrollbar-thumb:hover {
    background: #2563eb;
}
</style>
