<template>
  <div id="app">
    <header>
      <h1>VUE<span>CORDION</span></h1>
      <button @click="toggle">toggle</button>
    </header>
    <div v-if="showOrNot" class="faqs">
      <FAQ v-for="(faq, i) in faqs" :faq="faq" :index="i" :key="i"/>
    </div>
    {{ showOrNot ? '' : 'its falsy' }}
  </div>
</template>

<script>
import FAQ from './FAQ';
export default {
  name: 'App',
  components: {
    FAQ
  },
  data() {
    return {
      showOrNot: false,
      faqs: [
      {
        question: "1",
        answer: "great number",
        open: false,
      },
      {
        question: "2",
        answer: "great number, too",
        open: false,
      },
      {
        question: "3",
        answer: "great number as well",
        open: false,
      }
    ]
    }
  },
  methods: {
    toggle() {
      this.showOrNot = !this.showOrNot;
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  background-color: #eee;
  font-family: sans-serif;
}
header {
  background-color: #3c3c3c;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 15px;
}
header h1 {
  color: #eee;
  font-size: 28px;
  font-weight: 300;
  text-transform: uppercase;
}
header h1 span {
  color: #56e3b8;
  font-weight: 900;
}
</style>
