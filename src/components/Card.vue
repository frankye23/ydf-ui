<template>
  <h1 class="font-semibold text-2xl mt-4">Cards<span class="text-sm text-gray">(Using vannilla-tilt)</span></h1>

  <div class="tilt-card flex justify-center mt-4" data-tilt ref="labelDiv">
    <div class="w-1/4 rounded-2xl bg-gray-50 py-10 text-center ring-1 ring-inset ring-gray-900/5 lg:flex lg:flex-col lg:justify-center lg:py-16">
      <div class="mx-auto max-w-xs px-8">
        <p class="text-base font-semibold text-gray-600">Pay once, own it forever</p>
        <p class="mt-6 flex items-baseline justify-center gap-x-2">
          <span class="text-5xl font-bold tracking-tight text-gray-900">$349</span>
          <span class="text-sm font-semibold leading-6 tracking-wide text-gray-600">USD</span>
        </p>
        <a href="#" class="mt-10 block w-full rounded-md bg-indigo-600 px-3 py-2 text-center text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600">Get access</a>
        <p class="mt-6 text-xs leading-5 text-gray-600">Invoices and receipts available for easy company reimbursement</p>
      </div>
    </div>
  </div>
</template>
<script setup lang="ts">
import { ref, onMounted } from 'vue'
import VanillaTilt from 'vanilla-tilt';
const labelDiv = ref()


onMounted(()=>{
  const element = document.querySelector(".tilt-card") as any
  VanillaTilt.init(element);
})
</script>