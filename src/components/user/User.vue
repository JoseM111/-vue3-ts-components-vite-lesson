<!-- UserType.vue -->

// 🌀🌀💻 SCRIPT 💻🌀🌀
<script lang="ts">
import { defineComponent } from 'vue'
import { UserType } from "@/components/user/user.type"
// ⚫️⚫️☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰
export default defineComponent({
  name: 'User',
  emits: [ 'ageChange'],
  // Component options props
  props: {
    age: {
      type: Number as () => UserType['age'],
      required: true
    },
    name: {
      type: String as () => UserType['name'],
      required: true
    }
  },
  // Component options computed
  computed: {
    // Not directly updating the value. Creating a copy
    ageDoubled(): number {
      return this.age * 2
    }
  },
  // Component options methods
  methods: {
    updateAge() {
      //☰☰☰☰☰☰☰☰☰☰
      /** @$emit
       * Trigger an event on the current instance.
       * Any additional arguments will be passed
       * into the listener's callback function.
       * | */
      this.$emit('ageChange', 3)
    }
  },
  
})
</script>
<!-- 🌀🌀💻================================================= -->

// 🌀🌀💻 HTML 💻🌀🌀
<template>
  <h1>
    <b>The user is ( {{ age }} ) years old</b>
    <br>
    <b>The user name is ( {{ name }} )</b>
    <br>
    <b>Age doubled ( {{ ageDoubled }} )</b>
  </h1>
  
  <button @click="updateAge">
    Update Age
  </button>
</template>
<!-- 🌀🌀💻================================================ -->

// 🌀🌀💻 STYLES 💻🌀🌀
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h1 {
  color: mediumpurple;
}

button {
  font-size: 30px;
  border-radius: 12px;
  padding: 10px 20px;
  background: dodgerblue;
  color: white;
  cursor: pointer;
  
  &:hover {
    transition: all 0.45s ease-in-out;
    opacity: 0.85;
    background: mediumvioletred;
    font-family: "Nosifer", sans-serif;
  }
  
  &:active {
    opacity: 0.10
  }
}
</style>
<!-- 🌀🌀💻================================================ -->

