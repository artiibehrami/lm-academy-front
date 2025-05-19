<script setup>
import { onMounted, ref } from 'vue'

const quote = ref('')
const author = ref('')

const quotes = [
  { text: 'Success is not the key to happiness. Happiness is the key to success.', author: 'Albert Schweitzer' },
  { text: 'The only way to do great work is to love what you do.', author: 'Steve Jobs' },
  { text: 'Learning never exhausts the mind.', author: 'Leonardo da Vinci' },
  { text: 'Education is the most powerful weapon which you can use to change the world.', author: 'Nelson Mandela' },
  { text: 'The future belongs to those who believe in the beauty of their dreams.', author: 'Eleanor Roosevelt' },
  { text: 'The world would go on even without you. Don\'t take yourself so seriously.', author: 'Norman Vincent Peale' },
  { text: 'Learning is a treasure that will follow its owner everywhere', author: 'Chinese Proverb' }
]

const randomQuote = quotes[Math.floor(Math.random() * quotes.length)]

const fetchZenQuoteApi = async () => {
  try {
    const reponse = await fetch('http://localhost:8000/api/zen-quote')
    const data = await reponse.json()
    console.log('data', data)
    if (data.success) {
      quote.value = data.quote.text
      author.value = data.quote.author
    }
  } catch (error) {
    console.error('Error fetching quote:', error)
  }
}

onMounted(() => {
  fetchZenQuoteApi()
})
</script>

<template>
  <div class="h-full flex flex-col justify-around">
    <div class="welcome-message flex justify-center">
      <div class="w-[250px] md:w-[450px] text-center">
        <h1 class="text-3xl">
          Welcome to LM Academy Empowering Students with the Skills of Tomorrow
        </h1>
      </div>
    </div>

    <div class="api-quote flex justify-end">
      <div class="w-[250px] md:w-[450px] text-end space-y-4 text-2xl">
        <h1 class="italic font-gelasio text-[#003366]">
          {{ quote || randomQuote.text }}
        </h1>
        <p class="text-[#8694A9]">{{ author || randomQuote.author }}</p>
      </div>
    </div>
  </div>
</template>
