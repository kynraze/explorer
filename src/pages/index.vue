<script lang="ts" setup>
import { Icon } from '@iconify/vue';
import {
  useDashboard,
  LoadingStatus,
  type ChainConfig,
} from '@/stores/useDashboard';
import ChainSummary from '@/components/ChainSummary.vue';
import { computed, ref } from 'vue';
import { useBlockchain } from '@/stores';

const dashboard = useDashboard();

const keywords = ref('');
const chains = computed(() => {
  if (keywords.value) {
    return Object.values(dashboard.chains).filter(
      (x: ChainConfig) => x.chainName.indexOf(keywords.value) > -1
    );
  } else {
    return Object.values(dashboard.chains);
  }
});
const chainStore = useBlockchain()
</script>
<template>
  <div class="">
    <div class="flex md:!flex-row flex-col items-center justify-center mb-6 mt-14 gap-2">
      <div class="w-16 rounded-full">
        <svg version="1.0" xmlns="http://www.w3.org/2000/svg" 
          viewBox="0 0 150.000000 132.000000"
          preserveAspectRatio="xMidYMid meet">
          <g transform="translate(0.000000,132.000000) scale(0.100000,-0.100000)"
          :fill="chainStore.current?.themeColor||'#666CFF'" class=" dark:invert" stroke="none">
            <path d="M650 1289 c-236 -36 -452 -231 -516 -469 -26 -96 -24 -235 5 -330 36 -117 77 -187 166 -275 128 -129 263 -185 443 -185 116 0 192 19 297 73 153 79 281 242 320 408 19 82 19 216 -1 299 -41 176 -173 341 -335 418 -46 22 -104 44 -129 50 -71 17 -179 21 -250 11z m231 -165 c30 -9 80 -30 111 -46 45 -23 61 -27 77 -19 11 6 39 10 63 10 26 -1 33 -3 18 -6 -168 -28 -299 -132 -470 -374 -81 -114 -279 -339 -299 -339 -4 0 -22 24 -40 54 -141 234 -67 536 164 672 107 62 261 82 376 48z m262 -181 c61 -88 81 -151 85 -263 6 -156 -28 -246 -137 -364 -25 -27 -40 -46 -33 -42 8 5 12 -1 12 -18 0 -14 -2 -26 -4 -26 -2 0 -12 -3 -22 -7 -14 -5 -16 -2 -12 20 5 25 4 25 -19 10 -15 -10 -23 -25 -23 -43 0 -20 -6 -29 -21 -33 -18 -5 -20 -2 -16 19 2 13 4 24 3 24 -36 -11 -107 -39 -98 -40 22 0 12 -30 -14 -40 -35 -14 -35 -13 -24 15 l10 25 -88 -1 c-48 -1 -79 -3 -70 -6 28 -7 9 -33 -25 -33 -29 0 -29 1 -14 18 22 24 21 32 -1 32 -10 0 -50 16 -90 35 -40 19 -70 30 -67 25 3 -5 -3 -14 -13 -19 -15 -8 -23 -6 -37 9 -13 14 -31 20 -61 20 -32 0 -49 6 -64 23 -21 22 -21 22 -1 25 11 2 29 -6 40 -17 17 -17 25 -18 63 -10 147 34 274 146 437 387 96 142 242 312 267 312 6 0 23 -17 37 -37z m107 -577 c0 -8 -6 -19 -14 -25 -18 -15 -27 6 -14 32 10 19 28 14 28 -7z m-110 -50 c0 -8 -6 -19 -14 -25 -18 -15 -27 7 -12 31 11 18 26 15 26 -6z m-742 -13 c5 -18 -23 -16 -39 3 -11 14 -10 15 11 12 13 -1 25 -9 28 -15z m762 -47 c0 -7 -9 -21 -20 -31 -19 -18 -20 -17 -20 6 0 27 18 51 32 43 4 -3 8 -11 8 -18z m-750 -31 c10 -12 9 -16 -4 -21 -16 -6 -46 11 -46 27 0 15 37 10 50 -6z m150 -26 c0 -15 -21 -21 -48 -14 -25 6 -26 8 -9 20 18 13 57 9 57 -6z m503 -34 c-25 -19 -33 -18 -33 4 0 10 10 25 23 34 20 14 22 13 25 -5 2 -11 -5 -26 -15 -33z m-569 9 c20 -8 20 -20 0 -28 -19 -7 -57 11 -49 25 7 10 26 12 49 3z m286 -8 c0 -20 -16 -36 -36 -36 -26 0 -30 10 -12 28 11 11 48 17 48 8z m210 -25 c0 -17 -18 -31 -41 -31 -14 0 -11 38 4 43 25 11 37 7 37 -12z m-356 -17 c21 -8 2 -34 -24 -34 -24 0 -32 11 -19 27 13 15 20 16 43 7z m216 -8 c0 -20 -16 -36 -36 -36 -26 0 -30 10 -12 28 11 11 48 17 48 8z m-100 -15 c0 -17 -26 -30 -48 -24 -18 4 -20 8 -11 19 13 15 59 19 59 5z"/>
<path d="M500 768 l1 -203 30 35 c16 19 52 67 79 107 l50 71 0 96 0 96 -80 0 -80 0 0 -202z"/>
<path d="M862 584 l-43 -65 43 -70 43 -69 93 0 c78 0 93 2 89 15 -10 25 -167 255 -175 255 -4 0 -26 -30 -50 -66z"/>
          </g>
        </svg>
      </div>
      <h1 class="text-primary dark:invert text-3xl md:!text-6xl font-bold">
        {{ $t('pages.title') }}
      </h1>
      <div class="badge badge-primary badge-outline dark:invert mt-1 text-sm md:!mt-8">
        {{ $t('pages.tag') }}
      </div>
    </div>
    <div class="text-center text-base">
      <p class="mb-1">
        {{ $t('pages.slogan') }}
      </p>
      <h2 class="mb-6">{{ $t('pages.description') }}</h2>
    </div>
    <div
      v-if="dashboard.status !== LoadingStatus.Loaded"
      class="flex justify-center"
    >
      <progress class="progress progress-info w-80 h-1"></progress>
    </div>

    <div class="flex items-center rounded-lg bg-base-100  border border-gray-200 dark:border-gray-700 mt-10">
      <Icon icon="mdi:magnify" class="text-2xl text-gray-400 ml-3"/>
      <input :placeholder="$t('pages.search_placeholder')" class="px-4 h-10 bg-transparent flex-1 outline-none text-base" v-model="keywords" />
      <div class="px-4 text-base hidden md:!block">{{ chains.length }}/{{ dashboard.length }}</div>
    </div>

    <div
      class="grid grid-cols-1 gap-4 mt-6 md:!grid-cols-3 lg:!grid-cols-4 2xl:!grid-cols-5"
    >
      <ChainSummary
        v-for="(chain, index) in chains"
        :key="index"
        :name="chain.chainName"
      />
    </div>
  </div>
</template>

<style scoped>
 .logo path{
  fill: #171d30;
}
</style>
