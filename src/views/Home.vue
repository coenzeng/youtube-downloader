<template>
  <div class="home">
    <p ref="p">My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">Click Me</button>
    <input type="text" v-model="name" />
    <button @click="stopEffect1">Stop Watching</button>
  </div>
  <HelloWorld msg="Hello Vue 3 + Vite" />
</template>

<script>
import HelloWorld from "../components/HelloWorld.vue";
import { computed, ref } from "@vue/reactivity";
import { watchEffect } from "@vue/runtime-core";
// @ is an alias to /src

export default {
  name: "Home",
  setup() {
    //this runs before any lifecycle hook

    const p = ref(null);
    const name = ref("Coenwerew");
    const age = ref(40);

    const handleClick = () => {
      console.log(p, p.value);
      p.value.classList.add("test");
      name.value = "bro";
    };
    /*
    const name1 = computed(() => {

    })

    */
    const stopEffect = watchEffect(() => {
      console.log(name.value);
    });

    const stopEffect1 = () => {
      stopEffect();
    };
    return { name, age, handleClick, p, stopEffect1 }; //same as { name: name, age: age }
  },
};
</script>

<style lang="scss">
/* Define standard variables and values for website */
@import "../scss/reset.scss";
@import "../scss/_variables.scss";

/* Use the variables */
body {
  background-color: $bgcolor2;
  color: $textcolor;
  font-size: $fontsize;
}

p {
  color: $textcolor;
}
</style>
