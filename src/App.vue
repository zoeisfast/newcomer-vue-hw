<script setup>
import Ranking from "./components/Ranking.vue";
import CheerModal from "./components/CheerModal.vue";
</script>

<template>
  <main class="min-h-screen bg-gray-900 flex items-center justify-center p-0 md:p-6">
    <div
      class="relative w-full max-w-sm md:max-w-6xl bg-black overflow-hidden shadow-2xl border border-gray-700"
    >
      <div class="flex flex-col md:flex-row">
        <div class="w-full md:w-2/3">
          <img
            src="./assets/img/chatroom-video.png"
            alt="stream video"
            class="w-full h-full object-contain"
          />
        </div>

        <div class="relative w-full md:w-1/3">
          <img
            src="./assets/img/chatroom-content.png"
            alt="chatroom"
            class="w-full h-full object-cover"
          />

          <CheerModal v-if="true"></CheerModal>
        </div>
      </div>

      <Ranking v-if="false"></Ranking>
    </div>
  </main>
</template>

<style scoped></style>