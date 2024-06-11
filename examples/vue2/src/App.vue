<script>
export default {
  data() {
    return {
      count: 0,
      surveyKey: import.meta.env?.VITE_UB_SURVEY_KEY
    }
  },
  methods: {
    increment() { this.count += 1 }
  }
}
</script>

<template>
  <div id="app">
  <div>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
  </div>
  <button @click="increment">{{count}}</button>
  <hr />
  <button type="button" v-on:click="$userback.show()">Show</button>
  <button type="button" v-on:click="$userback.hide()">Hide</button>
  <hr />
  <button type="button" v-on:click="$userback.open('bug')">Open Bugs</button>
  <button type="button" v-on:click="$userback.open('general', 'screenshot')">Screenshot me!</button>
  <hr />
  <button type="button" @click="$userback.openSurvey(surveyKey)">Open Survey</button>
  <button type="button" @click="$userback.closeSurvey()">Close Survey</button>
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
