<script setup lang="ts">
defineProps<{
  isWrongPositionLetter?: boolean
  isSuccessLetter?: boolean
}>()
</script>

<template>
 <div :class="['shadow-xl text-white rounded bg-slate-600 w-12 h-12 md:w-14 md:h-14 lg:w-16 lg:h-16 flex justify-center items-center text-3xl font-semibold', { 'bg-yellow-500': isWrongPositionLetter }, { 'bg-green-500': isSuccessLetter }]">
 <slot/>
 </div>
</template>
