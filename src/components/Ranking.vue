<script setup>
import bgSrc from '../assets/img/ranking-bg.png'
import topCardBgSrc from '../assets/img/ranking-card-bg.png'
import trophy1Src from '../assets/img/ranking-trophy-1.png'
import trophy2Src from '../assets/img/ranking-trophy-2.png'
import trophy3Src from '../assets/img/ranking-trophy-3.png'
import activeRankSrc from '../assets/img/ranking-active-item.svg'
import emptyRankSrc from '../assets/img/ranking-empty-item.svg'

// 對應 Figma TOP1/2/3 卡片在 190px 區塊中的垂直位置
const topRanks = [
  {
    rank: 'TOP-2',
    name: 'A˙˙˙˙˙˙1',
    score: '43.8K',
    offset: 'mt-[99px]',
    gradient: 'from-[#4ceedb] to-[#2da1bd]',
    trophySrc: trophy2Src,
  },
  {
    rank: 'TOP-1',
    name: 'V˙˙˙˙˙˙1',
    score: '45.6K',
    offset: 'mt-[81px]',
    gradient: 'from-[#fff159] to-[#e5a400]',
    trophySrc: trophy1Src,
  },
  {
    rank: 'TOP-3',
    name: 'C˙˙˙˙˙˙1',
    score: '24.3K',
    offset: 'mt-[106px]',
    gradient: 'from-[#6cb3ff] to-[#00a4e5]',
    trophySrc: trophy3Src,
  },
]

const rankingItems = [
  { rank: 4, name: 'B˙˙˙˙˙˙7', score: '22.1K', active: true },
  { rank: 5, name: 'P˙˙˙˙˙˙7', score: '18.1K', active: true },
  { rank: 6, name: '待上榜', active: false },
  { rank: 7, name: '待上榜', active: false },
  { rank: 8, name: '待上榜', active: false },
  { rank: 9, name: '待上榜', active: false },
  { rank: 10, name: '待上榜', active: false },
]

const topCardBase =
  'relative flex h-[60px] w-full flex-col items-center rounded-t-[10px] bg-gradient-to-b px-2.5'

const rankingItemBase =
  'relative flex h-[58px] w-full items-center gap-1 overflow-hidden rounded-[10px] py-2 pr-4 shadow-[0_2px_8px_rgba(0,0,0,0.1)]'
</script>

<template>
  <div
    class="absolute inset-x-0 bottom-0 z-40 flex h-[570px] flex-col overflow-hidden rounded-t-2xl bg-[#272727] text-white md:hidden"
  >
    <img
      class="absolute inset-0 h-full w-full object-cover opacity-80"
      :src="bgSrc"
      alt=""
    />

    <!-- 排行榜標題區 -->
    <div class="relative z-10 flex h-[42px] w-full items-start justify-center px-3 pt-3">
      <h2 class="m-0 whitespace-nowrap text-center font-['Zen_Maru_Gothic'] text-[18px] font-black leading-none text-white [text-shadow:0_2px_1px_rgba(0,0,0,0.25)]">
        單場預測王
      </h2>

      <button
        class="absolute right-3 top-3 grid size-6 place-items-center"
        type="button"
      >
        <svg
          class="size-4"
          viewBox="0 0 16 16"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M3 3L13 13M13 3L3 13"
            stroke="white"
            stroke-width="2"
            stroke-linecap="round"
          />
        </svg>
      </button>
    </div>

    <!-- TOP 1 / 2 / 3 區塊 -->
    <div class="relative z-10 grid h-[190px] w-full shrink-0 grid-cols-[100px_100px_100px] justify-between px-[26px]">
      <div
        v-for="item in topRanks"
        :key="item.rank"
        class="flex w-[100px] flex-col drop-shadow"
        :class="item.offset"
      >
        <!-- TOP 卡片上半部 -->
        <div :class="[topCardBase, item.gradient]">
          <!-- TOP 卡片背景紋理 -->
          <img
            class="pointer-events-none absolute inset-0 h-full w-full rounded-t-[10px] object-cover"
            :src="topCardBgSrc"
            alt=""
          />

          <!-- TOP 文字、獎盃、得獎者 -->
          <div class="relative z-10 -mt-[42px] flex flex-col items-center">
            <!-- TOP 名次文字 -->
            <div class="whitespace-nowrap font-['Roboto'] text-[16px] font-black leading-none text-white [text-shadow:0_0_4px_#ffdc56]">
              {{ item.rank }}
            </div>

            <!-- TOP 文字距離獎盃 -->
            <img
              class="mt-[7px] h-[49px] w-[57px] object-contain"
              :src="item.trophySrc"
              alt=""
            />

            <!-- 獎盃距離得獎者名稱 -->
            <p class="mx-0 mt-[10px] mb-[6px] w-full truncate text-center font-['Roboto'] text-[14px] font-bold leading-none text-[#262626]">
              {{ item.name }}
            </p>
          </div>
        </div>

        <!-- TOP 卡片下半部：分數 -->
        <div class="flex h-6 w-full items-center justify-center rounded-b-[10px] bg-gradient-to-b from-[#6703c4] to-[#480a82] px-2.5">
          <p class="m-0 truncate text-center font-['Roboto'] text-[14px] font-bold leading-[18px] text-[#ffcc4d]">
            {{ item.score }}
          </p>
        </div>
      </div>
    </div>

    <!-- 第 4 名以後的排行榜列表 -->
    <div class="relative z-10 min-h-0 flex-1 overflow-hidden rounded-t-2xl">
      <div class="ranking-scroll h-full overflow-y-auto p-4">
        <ol class="m-0 flex list-none flex-col gap-3 p-0">
          <li
            v-for="item in rankingItems"
            :key="item.rank"
            :class="[
              rankingItemBase,
              item.active
                ? 'bg-gradient-to-r from-[rgba(72,0,138,0.7)] to-[rgba(109,35,176,0.7)]'
                : 'bg-[#1d1d1d]',
            ]"
          >
            <!-- 左側名次區 -->
            <div class="relative grid h-[68px] w-[59px] shrink-0 items-center">
              <!-- 裝飾底圖 -->
              <div class="absolute -left-2 -right-2 -top-1 -bottom-3">
                <img
                  class="block h-full w-full max-w-none"
                  :src="item.active ? activeRankSrc : emptyRankSrc"
                  alt=""
                />
              </div>

              <!-- 名次數字 -->
              <p
                class="relative z-10 my-0 mr-0 ml-[4px] w-10 text-center font-['Mitr'] text-[32px] font-semibold leading-none text-white"
                :class="{ 'opacity-10': !item.active }"
              >
                {{ item.rank }}
              </p>
            </div>

            <!-- 排行榜名稱 -->
            <p
              class="m-0 min-w-0 flex-1 truncate font-['Roboto'] text-[16px] font-bold leading-none text-[#c9c9c9]"
              :class="{ 'opacity-30': !item.active }"
            >
              {{ item.name }}
            </p>

            <!-- 排行榜分數 -->
            <p
              v-if="item.active"
              class="m-0 shrink-0 truncate text-right font-['Roboto'] text-[20px] font-bold leading-normal text-white"
            >
              {{ item.score }}
            </p>
          </li>
        </ol>
      </div>
    </div>
  </div>
</template>

<style scoped>
.ranking-scroll {
  scrollbar-width: none;
  -ms-overflow-style: none;
}

.ranking-scroll::-webkit-scrollbar {
  display: none;
}
</style>