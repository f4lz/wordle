<script setup lang="ts">
import RulesList from './components/RulesList.vue';
import WordElement from './components/WordElement.vue';
import WordElementWrapper from './components/WordElementWrapper.vue';
import { ref } from 'vue';

const letters: any = ref([['', '', '', '', ''], ['', '', '', '', ''], ['', '', '', '', ''], ['', '', '', '', ''], ['', '', '', '', '']]) 
const index = ref(0)

document.addEventListener('keydown', (e) => {
  for ( const letter of alphabetList ) {
    if ( e.key.toLowerCase() === letter.toLowerCase() ) {
      // if ( enteringWork.value.length < 6 ) {
        letters.value[index.value] = `${letter}`
        index.value++
      // } else {
      // }
    } 
  }
  if ( e.key === 'Escape') {
    return
  }
  if ( e.key === 'Backspace') {
    letters.value[index.value] = ''
    index.value < 0  ? index.value = 0 : index.value--
    return
  }
})

const alphabetList = [ 'А', 'Б', 'В', 'Г', 'Д', 'Е', 'Ё', 'Ж', 'З', 'И', 'Й', 'К', 'Л', 'М', 'Н', 'О', 'П', 'Р', 'С', 'Т', 'У', 'Ф', 'Х', 'Ц', 'Ч', 'Ш', 'Щ', 'Ъ', 'Ы', 'Ь', 'Э', 'Ю', 'Я' ]

// const currentWord = "Данные".split('')

</script>

<template>
  <div class="bg-neutral-700 h-screen flex flex-col gap-y-6 justify-center items-center">
      <div class="flex flex-col gap-3">
       <WordElementWrapper v-for="(letter, index) in letters" :key="index">
        <WordElement v-for="(letters, index) in letter" :key="index">
        </WordElement>
        </WordElementWrapper>
      </div>
      <div class="container flex flex-col gap-y-4 max-w-sm justify-center">
        <h1 class="text-center">Правила игры:</h1>
        <p>
          Wordle - это игра, в которой вы должны угадать загаданное пятибуквенное слово, имея всего 6 попыток. После каждой попытки вам дают подсказки о правильности букв в слове:
      </p>
      <RulesList/>
      <p>Ваша задача - с помощью этих подсказок угадать загаданное слово до исчерпания 6 попыток.</p>
      </div>
  </div>
</template>
