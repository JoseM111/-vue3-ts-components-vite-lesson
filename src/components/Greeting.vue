<!-- Greeting.vue -->

// 🌀🌀💻 SCRIPT 💻🌀🌀
<script lang="ts">
import { defineComponent } from 'vue'
import { UserType } from "@/components/user/user.type"
// ⚫️⚫️☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰
export default defineComponent({
  name: 'Greeting',
  // Component options props
  props: {
    age: {
      type: Number as () => UserType['age'],
      required: true
    },
  },
  // Component options data
  data() {
    return {
      msg: 'Hola Mundo'
    }
  },
})
</script>
<!-- 🌀🌀💻================================================= -->

// 🌀🌀💻 HTML 💻🌀🌀
<template>
  
  <h1 v-if="age > 25">
    <b>{{ msg }}</b>
  </h1>
  
  <p v-else>
    <b>You must be 25 years or older to view this Greeting</b>
  </p>
  
</template>
<!-- 🌀🌀💻================================================ -->

// 🌀🌀💻 STYLES 💻🌀🌀
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
$colorRed: red;

h1 {
  color: $colorRed;
}

p {
  font-family: Iceland, sans-serif;
  color: green;
}
</style>
<!-- 🌀🌀💻================================================ -->












