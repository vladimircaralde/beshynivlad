<script setup>
  import { ref} from 'vue';

  const beshyText = ref("")
  const outputBeshyText = ref("")

  const convertBeshy = () => {
    const arrBeshy = beshyText.value.split(" ")
    outputBeshyText.value = arrBeshy.join(" 🤸🏻‍♀️ ")
  }

  const copyToClipboard = () => {
    navigator.clipboard.writeText(outputBeshyText.value)
  }
</script>

<template>
  <div class="w-[500px] mx-auto mt-20">
    <h1 class="text-center text-3xl font-semibold bg-[#F4F2FF] py-3 rounded-3xl">🤸🏻‍♀️ Beshy App 🤸🏻‍♀️</h1>
    <textarea v-model="beshyText" type="text" class="w-full overflow-hidden rounded-xl border-2 mt-10 border-[#6366FA] p-4 focus:outline-[#6366FA]" rows="4"></textarea>
    <div class="flex justify-end my-5">
      <button @click="convertBeshy" class="rounded-full px-3 py-1 bg-[#F4F2FF] text-xl hover:bg-[#b3a6ff]">Go Beshy 🤸🏻‍♀️</button>
    </div>
    <div v-if="outputBeshyText" class="bg-[#F4F2FF] rounded-lg p-5 pt-10 relative">
      <div class="absolute top-3 right-3" @click="copyToClipboard">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 hover:text-[#6366FA]">
          <path stroke-linecap="round" stroke-linejoin="round" d="M15.666 3.888A2.25 2.25 0 0013.5 2.25h-3c-1.03 0-1.9.693-2.166 1.638m7.332 0c.055.194.084.4.084.612v0a.75.75 0 01-.75.75H9a.75.75 0 01-.75-.75v0c0-.212.03-.418.084-.612m7.332 0c.646.049 1.288.11 1.927.184 1.1.128 1.907 1.077 1.907 2.185V19.5a2.25 2.25 0 01-2.25 2.25H6.75A2.25 2.25 0 014.5 19.5V6.257c0-1.108.806-2.057 1.907-2.185a48.208 48.208 0 011.927-.184" />
        </svg>
      </div>
      <p class="text-lg">{{ outputBeshyText }}</p>
    </div>
  </div>
</template>
