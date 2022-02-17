<template>
  <div class="about">
    <p>
      This is a small project to learn Nuxt.js, following steps from
      <a href="https://www.youtube.com/watch?v=ltzlhAxJr74">Traversy Media</a>.
      <br>
      Jokes API are from
      <a href="https://icanhazdadjoke.com/">https://icanhazdadjoke.com</a>
      <br>
      <span>
        Thanks for browsing. Have fun!
      </span>
    </p>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: 'About This App'
    }
  }
}
</script>

<style scoped>
  p{
    line-height: 2;
  }
  p a{
    text-decoration: underline;
  }
  p span{
    font-weight: 600;
  }
</style>