<!-- App.vue -->

// 🌀🌀💻 SCRIPT 💻🌀🌀
<script lang="ts">
import { defineComponent } from 'vue'
import Greeting from "@/components/Greeting.vue"
import User from "@/components/user/User.vue"
// ⚫️⚫️☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰☰
export default defineComponent({
  name: 'App',
  components: {
    Greeting, User
  },
  // Component options data
  data: () => ({
    age: 20,
    name: 'Bobby111',
  }),
  // Component options methods
  methods: {
    updateAge(num: number) {
      //☰☰☰☰☰☰☰☰☰☰
      this.age += num
    }
  }
})
</script>
<!-- 🌀🌀💻================================================= -->

// 🌀🌀💻 HTML 💻🌀🌀
<template>
  <div class="container">
    
    <!--⚫️ GreetingComponent ⚫️-->
    <Greeting :age="age" />

    <!--⚫️ UserComponent ⚫️-->
    <User :age="age"
          :name="name"
          @ageChange="updateAge"
    />
    
  </div>
</template>
<!-- 🌀🌀💻================================================ -->

// 🌀🌀💻 STYLES 💻🌀🌀
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.container {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  height: 100%;
  width: 100%;
  background: black;
  font-family: "Amazon Ember", serif;
  text-align: center;
  padding-top: 400px;
  font-size: 43px;
}
</style>
<!-- 🌀🌀💻================================================ -->

