<template>
  <div class="home">
    home
    <p ref="para">My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">Click Me</button>
  </div>
</template>

<script>
import { ref } from '@vue/reactivity';


export default {
  name: 'Home',
  setup() {
    console.log(this);

    const para = ref(null);

    let name = 'mario';
    let age = 20;

    const handleClick = () => {
      console.log(para, para.value);
      para.value.classList.add('active');
      para.value.textContent = 'hello, ninjas';
    }

    return { name, age, handleClick, para };
  }
}
</script>
