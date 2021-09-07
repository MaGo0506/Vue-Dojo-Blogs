<template>
  <div class="home">
    home
    <p ref="para">My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">Click Me</button>
    <button @click="age++">Add 1 to Age</button>
    <input type="text" v-model="name">
  </div>
</template>

<script>
import { ref } from '@vue/reactivity';


export default {
  name: 'Home',
  setup() {

    // const para = ref(null);

    const name = ref('mario');
    const age = ref(20);

    const handleClick = () => {
      name.value = 'yoshi';
      age.value = 30
    }

    return { name, age, handleClick };
  }
}
</script>
