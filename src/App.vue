<script setup lang="ts">
import RulesList from './components/RulesList.vue';
import WordElement from './components/WordElement.vue';
import UiGrid from './components/ui/UiGrid.vue';
import { ref } from 'vue';

// const russianAlphabetRegex = /[A-Za-z]/;

const enteringWork: any = ref([])

document.addEventListener('keydown', (e) => {
  for ( const [ index, letter ] of alphabetList.entries() ) {
    if ( e.key.toLowerCase() === letter.toLowerCase() ) {
      if ( enteringWork.value.length < 6 ) {
        enteringWork.value.push(letter)
      } else {
        console.log('текущее слово', enteringWork.value)
      }
    } 
  }
  if ( e.key === 'Escape') {
    alert("value")
    return
  }
})

const alphabetList = [ 'А', 'Б', 'В', 'Г', 'Д', 'Е', 'Ё', 'Ж', 'З', 'И', 'Й', 'К', 'Л', 'М', 'Н', 'О', 'П', 'Р', 'С', 'Т', 'У', 'Ф', 'Х', 'Ц', 'Ч', 'Ш', 'Щ', 'Ъ', 'Ы', 'Ь', 'Э', 'Ю', 'Я' ]

const currentWord = "Данные".split('')

</script>

<template>
  <div class="bg-neutral-700 h-screen flex flex-col gap-y-6 justify-center items-center">
      <UiGrid>
       <WordElement :class="`wordElement${index}`" v-for="(_, index) in 25" :key="index"/>
      </UiGrid>
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
