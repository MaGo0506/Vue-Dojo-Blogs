<template>
  <div class="home">
    <h1>Home</h1>
    <PostList :posts="posts" />
  </div>
</template>

<script>
import PostList from '../components/PostList.vue'
import { ref } from '@vue/reactivity';


export default {
  name: 'Home',
  components: { PostList },
  setup() {
    const posts = ref([ 
        {title: 'Welcome to the blog', body: 'Lorem ipsum', id: 1},
        {title: 'Top 5 CSS tipts', body: 'Lorem ipsum', id: 2},
     ])

    
    return { posts };
  }
}
</script>
