<script setup lang="ts">
defineProps<{
  title: string;
  type: string;
  placeholder: string;
  buttonText: string;
}>();

const emit = defineEmits(['onSubmit']);
function handleSubmit(): void {
  emit('onSubmit');
}
</script>

<template>
  <div class="flex justify-center mt-20">
    <img src="/robot.png" class="h-[180px]" alt="" />
  </div>

  <form
    @submit.prevent="handleSubmit"
    class="w-full pt-10 pb-20 px-4 bg-[#2B2F3B] rounded-2xl"
  >
    <h2 class="text-xl xl:text-3xl mb-8">{{ title }}</h2>

    <input
      :type="type"
      :placeholder="placeholder"
      class="w-full px-4 py-6 bg-[#252832] rounded-lg mb-6 text-sm"
    />

    <button
      type="submit"
      class="bg-linear-90 from-[#D64059] to-[#5E489D] text-white font-bold px-16 py-2 rounded-lg w-full flex justify-center cursor-pointer text-sm"
    >
      {{ buttonText }}
    </button>
  </form>
</template>
