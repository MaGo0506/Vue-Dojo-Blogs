<template>
  <div class="home">
    <h1>Home</h1>
    <input type="text" v-model="search">
    <p>Search term - {{ search }}</p>
    <div v-for="name in matchingNames" :key="name">{{ name }}</div>
  </div>
</template>

<script>
import { computed, ref } from '@vue/reactivity';
import { watch, watchEffect } from '@vue/runtime-core';


export default {
  name: 'Home',
  setup() {
    const search = ref('')
    const names = ref([ 'mario', 'yoshi', 'luigi', 'toad', 'bowser', 'koopa', 'peach' ])

    watch(search, () => {
      console.log('watch function ran');
    })

    watchEffect(() => {
      console.log('watchEffect function ran', search.value);
    })

    const matchingNames = computed(() => {
      return names.value.filter((name) => name.includes(search.value))
    })

    return { names, search, matchingNames };
  }
}
</script>
