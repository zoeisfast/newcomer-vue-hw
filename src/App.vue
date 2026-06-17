<script setup></script>

<template>
  <main class="min-h-screen bg-gray-900 flex items-center justify-center p-6">
    <!-- Phone frame -->
    <div
      class="w-full max-w-sm md:max-w-6xl bg-black overflow-hidden shadow-2xl border border-gray-700"
    >
      <!-- Inner content: vertical on mobile, horizontal on md+ -->
      <div class="flex flex-col md:flex-row">
        <!-- Video section -->
        <div class="w-full md:w-2/3">
          <img
            src="./assets/img/chatroom-video.png"
            alt="stream video"
            class="w-full h-full object-contain"
          />
        </div>
        <!-- Chat section -->
        <div class="w-full md:w-1/3">
          <img
            src="./assets/img/chatroom-content.png"
            alt="chatroom"
            class="w-full h-full object-cover"
          />
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped></style>
