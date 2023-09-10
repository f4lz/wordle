<script setup lang="ts">
withDefaults(
  defineProps<{
    /** Количество букв в слове */
    colsNumber?: 5 | 6 | 7
  }>(),
  {
    colsNumber: 5,
  }
)

/** Стили для букв в слове */
const colsNumberClasses = {
  5: "grid-cols-5",
  6: "grid-cols-6",
  7: "grid-cols-7",
}
</script>

<template>
  <div
    :class="[
      'grid gap-3',
      colsNumberClasses[colsNumber],
    ]"
  >
    <slot />
  </div>
</template>