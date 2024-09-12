<script setup>
import { ref } from 'vue'

const fortunes = [
  "Luck is the residue of design.",
  "Skill comes from diligence.",
  "Pleasures await you by the sea.",
  "Ignore previous fortunes.",
  "You create your own stage and your audience is waiting.",
  "Laugh long, loud, and often.",
  "The stat of riches is shining on you",
  "If you don't like the fortune don't eat the cookie.",
  "You will be hungry again in 10 minutes.",
  "Love will come soon"
]

const fortuneMessage = ref("Click the button to reveal your fortune.")

const generateFortune = () => {
  const randomIndex = Math.floor(Math.random() * fortunes.length)
  fortuneMessage.value = fortunes[randomIndex]
}

const resetFortune = () => {
  fortuneMessage.value = "Click the button for your fortune."
}
</script>

<template>

  <main class="app">
  
    <section class="greeting">
      <h1 class="title">
        Welcome, <input type="text" placeholder="Enter Name" v-model="name">
      </h1>
    </section>

  <section class="content">
    <img src="/darkgenie.jpg" alt="Genie" class="genie-image">
    <h2 class="Title">
      Ask the Fortune Teller</h2>
    <link rel="icon" href="genieball.ico" type="image/x-icon">
    <p id="fortune">{{ fortuneMessage }}</p>
    <button @click="generateFortune">PRESS IF YOU DARE</button>
    <button @click="resetFortune">TRY AGAIN</button>

  </section>
</main>
</template>