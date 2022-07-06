<template>
  <div>
    <h1>Home</h1>
    <nuxt-link to="/">home</nuxt-link>
    <nuxt-link to="/test">test</nuxt-link>
    <div v-for="n in 30" :key="n">
      <component
        :is="n % 2 === 0 ? 'TestComponent' : 'TestComponentSecond'"
        :item="items[n]"
      ></component>
    </div>
  </div>
</template>
<style scoped>
h1 {
  font-size: 50px;
}
</style>
<script>
export default {
  name: "IndexPage",
  async asyncData({ params, $axios }) {
    let response = await fetch("https://jsonplaceholder.typicode.com/todos");
    response = await response.json();
    return { items: response };
  },
};
</script>
