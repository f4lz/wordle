<script setup lang="ts">
defineProps<{
  isWrongPositionLetter?: boolean
  isSuccessLetter?: boolean
}>()
</script>

<template>
 <div :class="['shadow-xl text-white rounded bg-slate-600 w-16 h-16 flex justify-center items-center text-3xl font-semibold', { 'bg-yellow-500': isWrongPositionLetter }, { 'bg-green-500': isSuccessLetter }]">
 <slot/>
 </div>
</template>
