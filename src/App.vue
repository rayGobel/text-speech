<template lang="pug">
  div#app
    .container.grid-lg
      .columns

        .col-8.col-mx-auto
          h1 Built With Vue.js

        .col-8.col-mx-auto
          .input-group
            input.form-input(type="text" :placeholder="inputPlaceholder" v-model="inputText")
            button.btn.btn-primary.input-group-btn(v-on:click.prevent="convertToSpeech") Submit
</template>

<script>
/* global responsiveVoice */
export default {
  data () {
    return {
      'inputText': '',
      'inputPlaceholder': 'hello!'
    }
  },
  name: 'app',
  mounted () {
    responsiveVoice.speak(this.inputPlaceholder)
  },
  methods: {
    convertToSpeech () {
      if (this.inputText) {
        responsiveVoice.speak(this.inputText)
      }
    }
  }
}
</script>

<style>
#app {
  margin-top: 10em;
  text-align: center;
}
</style>
