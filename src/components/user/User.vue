<!-- UserType.vue -->

// 🌀🌀💻 SCRIPT 💻🌀🌀
<script lang="ts">
import { defineComponent, PropType } from 'vue'
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
      type: String as PropType<UserType['name']>,
      required: true
    },
    ageChangeFn: Function // or Function:<-- Works too
  },
  // Component options computed
  computed: {
    // Not directly updating the value.
    // Creating a copy then updating that
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
  
  <div class="btnContainer">
    <!-- $emit: events. does get logged in browser debugger -->
    <button @click="updateAge">
      Update age with [EVENT]
    </button>
    
    <!-- callbacks. does not get logged in browser debugger -->
    <button @click="ageChangeFn(3)">
      Update age with [CALLBACK]
    </button>
  </div>
  
</template>
<!-- 🌀🌀💻================================================ -->

// 🌀🌀💻 STYLES 💻🌀🌀
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h1 {
  color: mediumpurple;
}

.btnContainer {
  // ⚫️⚫️☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰
  button {
    margin: 0 20px;
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
  
}
</style>
<!-- 🌀🌀💻================================================ -->

