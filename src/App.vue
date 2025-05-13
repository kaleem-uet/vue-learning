
<script setup>
import { ref } from 'vue'

// A "ref" is a reactive data source that stores a value.
// Technically, we don't need to wrap the string with ref()
// in order to display it, but we will see in the next
// example why it is needed if we ever intend to change
// the value.
const message = ref('Hello World!')
function reverseMessage() {
   message.value=message.value.split('').reverse().join('')
    
}
function notify() {
    alert("navigation was prevented")
  }
</script>

<template>
  <h4>{{ message}}</h4>
  <button @click="reverseMessage">
    Reverse Message
  </button>
  <button @click="message += '!'">
    Append "!"
  </button>
  <a href="https://vuejs.org" @click.prevent="notify">
     link with e.preventDefault()
  </a>
</template>

<style>
button,a{
  display:block;
   margin-bottom: 1em;
}

</style>