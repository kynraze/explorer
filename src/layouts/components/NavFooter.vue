<template>
  <!-- footer -->
  <footer
    class="flex items-center h-12 mt-5 text-sm bg-gray-100 dark:bg-[#171d30] py-2 z-10 w-full"
  >
    <div class="flex flex-1">
      &copy;&nbsp;
      {{ new Date().getFullYear() }}&nbsp;
      By&nbsp;
      <a
        class="link link-primary no-underline"
        href="https://kynraze.com"
        target="_blank"
        rel="noopener noreferrer"
        >Kynraze</a
      >
    </div>
    <div
      class="hidden md:!block"
    >
      <a
        class="link link-primary no-underline mr-4"
        href="https://github.com/ping-pub/explorer/blob/master/LICENSE"
        target="noopener noreferrer"
        >License</a
      >
      <a
        class="link link-primary no-underline"
        href="https://github.com/ping-pub/explorer"
        target="noopener noreferrer"
        >Github</a
      >
    </div>
  </footer>
</template>
