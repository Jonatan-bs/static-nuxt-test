<!-- Please remove this file from your project -->
<template>
  <div>
    <div class="item" v-if="title" :style="{backgroundColor: color}">
      {{ title }}
    </div>
  </div>
</template>

<style scoped>
  .item{
    width: 100%;
    padding: 20px;
    color: #fff;
    margin-bottom: 5px;
  }
</style>

<script>
export default {
  name: "TestComponentSecond",
  props: ['item'],
  computed: {
        // Going to make some small js tweaks
        title() {
            return this.item?.title
        },
        color() {
            return  "yellow"
        }
    },

};
</script>
