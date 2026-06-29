<script setup>
import juiceSrc from '../assets/img/juice.png'
import coffeeSrc from '../assets/img/coffee.png'
</script>

<template>
  <div
    role="alert"
    class="cheer-modal-enter absolute left-[12px] right-[12px] bottom-[60px] z-50 flex min-h-[56px] items-center gap-5 rounded-lg border border-red-600 bg-[rgba(147,42,0,0.9)] p-2 text-white md:hidden"
  >
    <div class="flex min-w-0 flex-1 flex-col items-start gap-1 text-xs font-normal leading-[18px]">
      <p class="m-0 leading-[18px]">
        <span class="font-bold">Angel : </span>
        <span>恭喜大佬贏了一單！</span>
      </p>

      <p class="m-0 leading-[18px]">
        要賞杯飲品跟主播慶祝一下嗎？
      </p>
    </div>

    <div class="ml-auto flex shrink-0 items-center gap-2.5">
      <button
        class="relative flex min-h-[30px] w-[66px] shrink-0 items-center justify-center rounded bg-gradient-to-t from-[#ff7b14] to-[#ff5e56] pl-[30px] pr-3"
        type="button"
      >
        <span class="flex min-h-6 w-6 flex-col items-center justify-center">
          <span class="min-h-[14px] max-w-6 break-words text-center text-xs font-bold leading-[12px]">果汁</span>
          <span class="min-h-2.5 text-center text-[10px] leading-[10px]">$5</span>
        </span>

        <span class="absolute -left-[10px] -top-[5px] size-[38px] overflow-hidden">
          <img
            class="h-full w-full object-contain object-center"
            :src="juiceSrc"
            alt=""
          />
        </span>
      </button>

      <button
        class="relative flex min-h-[30px] w-[66px] shrink-0 items-center justify-center rounded bg-gradient-to-t from-[#ff7b14] to-[#ff5e56] pl-[30px] pr-3"
        type="button"
      >
        <span class="flex min-h-6 w-6 flex-col items-center justify-center">
          <span class="min-h-[14px] max-w-6 break-words text-center text-xs font-bold leading-[12px]">咖啡</span>
          <span class="min-h-2.5 text-center text-[10px] leading-[10px]">$1</span>
        </span>

        <span class="absolute -left-[10px] -top-[5px] size-[38px] overflow-hidden">
          <img
            class="h-full w-full object-contain object-center"
            :src="coffeeSrc"
            alt=""
          />
        </span>
      </button>
    </div>

    <button
      class="absolute right-[-8px] top-[-8px] grid size-4 place-items-center rounded-full bg-white"
      type="button"
    >
      <svg
        class="size-[8px]"
        viewBox="0 0 10 10"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M1 1L9 9M9 1L1 9"
          stroke="#343434"
          stroke-width="2"
          stroke-linecap="round"
        />
      </svg>
    </button>
  </div>
</template>

<style scoped>
.cheer-modal-enter {
  animation: cheer-slide-up 360ms ease-out both;
}

@keyframes cheer-slide-up {
  from {
    opacity: 0;
    transform: translateY(24px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>