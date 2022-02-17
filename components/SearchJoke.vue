<template>
  <form @submit.prevent="onSubmit" @keyup.enter="onSubmit">
    <input type="text" v-model="text" placeholder="Search for a joke" />
    <input type="submit" value="Search">
  </form>
</template>

<script>
export default {
  name: 'SearchJoke',
  data() {
    return {
      text: ''
    }
  },
  methods: {
    onSubmit() {
      this.$emit('onSearch', this.text)
      this.text = ''
    }
  }
}
</script>

<style>
input{
  height: 28px;
}
</style>