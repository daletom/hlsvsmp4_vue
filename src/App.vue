<script setup>
  import {IxVideo} from '@imgix/ix-video';
  import TheHeader from './components/TheHeader.vue'
  import TheFooter from './components/TheFooter.vue'
  import {ref} from 'vue';
</script>
<script>
  export default {
    methods: {
      warn(message, event) {
        console.warn(message, event.detail);
      },
    },
  };
</script>

<template>
  <div class="relative overflow-hidden bg-white">
    <div class="mx-auto max-w-7xl">
      <div class="relative z-10 pb-8 bg-white sm:pb-16 md:pb-20 lg:max-w-2xl lg:w-full lg:pb-28 xl:pb-32">
        <svg class="absolute inset-y-0 right-0 hidden w-48 h-full text-white transform translate-x-1/2 lg:block" fill="currentColor" viewBox="0 0 100 100" preserveAspectRatio="none" aria-hidden="true">
          <polygon points="50,0 100,0 50,100 0,100" />
        </svg>

        <TheHeader />

        <main class="px-4 mx-auto mt-10 max-w-7xl sm:mt-12 sm:px-6 md:mt-16 lg:mt-20 lg:px-8 xl:mt-28">
          <div class="sm:text-center lg:text-left">
            <h1 class="text-4xl font-extrabold tracking-tight text-gray-900 sm:text-5xl md:text-6xl">
              <span class="block 3xl:inline">imgix Demos</span>
              {{ ' ' }}
              <span class="block text-5xl text-orange-600 xl:inline">HLS vs MP4</span>
            </h1>
            <p class="mt-3 text-base text-gray-500 sm:mt-5 sm:text-lg sm:max-w-xl sm:mx-auto md:mt-5 md:text-xl lg:mx-0">This app is used to showcase the user experience of playing an mp4 vs an HLS video with imgix. To test this, right-click on the browser and select "inspect", click the Network tab, change the speed to Fast 3G, and make sure the "disable cache" button next to it is selected.</p>
            <div class="mt-5 sm:mt-8 sm:flex sm:justify-center lg:justify-start">
              <div class="rounded-md shadow">
                <a href="https://dashboard.imgix.com/sign-up" class="flex items-center justify-center w-full px-8 py-3 text-base font-medium text-white bg-orange-600 border border-transparent rounded-md hover:bg-indigo-700 md:py-4 md:text-lg md:px-10"> TRY IT FREE </a>
              </div>
              <div class="mt-3 sm:mt-0 sm:ml-3">
                <a href="https://ixdemos.vercel.app/" class="flex items-center justify-center w-full px-8 py-3 text-base font-medium text-indigo-700 bg-indigo-100 border border-transparent rounded-md hover:bg-indigo-200 md:py-4 md:text-lg md:px-10"> See Something Else? </a>
              </div>
            </div>
          </div>
        </main>
         
      </div>
    </div>
    <div class="lg:absolute lg:inset-y-0 lg:right-0 lg:w-1/2">
      <img class="object-cover w-full h-56 sm:h-72 md:h-96 lg:w-full lg:h-full" src="https://tom.imgix.net/hlsvsmp4.png?w=1200&auto=format,compress&cs=srgb" alt="Header Image for HLS vs MP4" />
    </div>
  </div>
  
   <section aria-labelledby="collections-heading" class="min-h-screen px-4 py-12 bg-gray-800 sm:px-6 lg:px-8">
        <div class="px-4 mx-auto max-w-7xl sm:px-6 lg:px-8">
          <div class="max-w-2xl py-16 mx-auto sm:py-24 lg:py-32 lg:max-w-none">
            <h2 id="collections-heading" class="text-2xl font-extrabold text-center text-white">Testing HLS (Left) vs MP4 (Right)</h2>
            <h3 id="collections-heading" class="text-lg font-extrabold text-center text-white">Try Throttling Your Network Tab to 3G to See HLS Adapt to Lower Quality Networks. Press play on both videos.</h3>

            <div class="mt-6 space-y-12">
              <div class="relative group">
                <div class="relative w-full overflow-hidden bg-white border-2 h-120">
                  <ix-video
                    controls
                    source="https://ix-www.imgix.video/colombia.mov?fm=mp4"
                    type="video/mp4"
                    @error="(event) => warn('error:', event)"
                    class="object-cover object-center w-full h-full vjs-loading-spinng"
                    >
                  </ix-video>
                </div>
                </div>
              </div>
            </div>
          </div>
      </section>
      <TheFooter />
</template>

<style>
.vjs-loading-spinner {
  width: 250px;
  height: 250px;
  border: 12px solid white;
  border-radius: 125px;
  top: 40%;
  left: 45%;
}
</style>