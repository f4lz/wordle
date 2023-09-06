<script setup lang="ts">
defineProps<{
  isWrongPositionLetter?: boolean
  isSuccessLetter?: boolean
}>()
</script>

<template>
 <div :class="['shadow-xl text-white rounded bg-slate-600 w-16 h-16', { 'bg-yellow-500': isWrongPositionLetter }, { 'bg-green-500': isSuccessLetter }]"/>
</template>
