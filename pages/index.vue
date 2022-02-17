<template>
  <div>
    <h3>Hello there!</h3>
    <p>You wanna hear some silly jokes?</p>
    <p>Go to
      <nuxt-link to="/jokes" style="text-decoration:underline;">JokesPage</nuxt-link>   
      to see what's out there...
    </p>
  </div>
</template>

<script>
export default {
  name: 'IndexPage'
}
</script>

<style scoped>
  p{
    font-size: 18px;
  }
</style>
