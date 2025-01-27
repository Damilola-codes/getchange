<template>
<div class="flex h-screen">
    <div class="w-2/5 bg-blue-600 relative">
      <div class="absolute inset-0">
        <img :src="`/public/img/${selectedImage}`"
        class="w-full h-full object-cover" alt="">
        <div class=" inset-0 absolute">
          <div class="w-full h-full flex flex-col justify-end items-center pb-24 text-white">
           <div class="text-xl font-semibold">No Hassles</div> 
           <div class="w-1/2 text-center font-light text-lg my-2">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod.</div>
           <div class="flex items-center space-x-4">
            <div class="size-5 flex items-center justify-center border rounded-full"
            :class=" selectedImage === image ? 'border-gray-400' : 'border-transparent'"
            v-for="image in images" :key="image">
              <button class="size-2.5 rounded-full border"     
              :class= "selectedImage === image ? 'bg-green-700' : 'bg-gray-200' "
              @click="selectedImage = image"></button>
            </div>
           </div>
          </div>
        </div>
      </div>
    </div>
    <div class="text-center w-3/5 h-screen flex flex-col"> 
      <div class="w-full h-full">
        <slot>tetetetet</slot>
      </div>
      <div class="flex items-center justify-between text-sm font-light text-gray-500">
      <div>
        By signing up, you agree to our <a href="#" class="text-green-500 font-semibold">Terms</a> and <a href="#" class="text-green-500 font-semibold">Privacy Policy</a>
      </div>
      <div>
        © 2019 Tinylabs. All rights reserved.
      </div>
    </div>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return({
      selectedImage: 'layoutbanner.png',
      images: [
        'layoutbanner.png',
        'layoutbanner2.png',
      ]
    })
  }
}
</script>