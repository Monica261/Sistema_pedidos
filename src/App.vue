<template>
  <Comments />
</template>

<script>
import Comments from './components/Comments'

export default {
  name: 'app',
  components: {
    Comments
  }
}
</script>

<style>
body{
  background: linear-gradient(90deg, rgba(2,0,36,1) 0%, rgba(9,96,121,1) 100%, rgba(0,212,255,1) 100%);
}

h1{
  color:#fff;
}
</style>
