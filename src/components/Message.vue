<template>
  <div class="fixed top-0 left-0 w-full h-full flex items-center justify-center">
    <div v-if="showToast" class="bg-green-500 text-white py-2 px-4 rounded">
      {{ message }}
    </div>
  </div>
</template>

<script lang="ts">
import { ref } from 'vue';

export default {
  name: 'ToastComponent',
  setup() {
    const showToast = ref(false);
    const message = ref('');

    function displayToast(msg: any) {
      message.value = msg;
      showToast.value = true;
      setTimeout(() => {
        showToast.value = false;
      }, 3000);
    }

    return {
      showToast,
      message,
      displayToast,
    };
  },
};
</script>