<script setup lang="ts">

const rulesList = [ "Зеленая буква: правильная буква на правильной позиции.", "Желтая буква: правильная буква, но не на той позиции.", "Серая буква: буква не входит в загаданное слово." ]

</script>

<template>
  <ul class="list-decimal list-inside flex flex-col gap-y-2">
    <li v-for="(rule, index) of rulesList" :key="rule + index">
      {{ rule }}
    </li>
  </ul>
</template>
