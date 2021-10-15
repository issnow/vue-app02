<template>
  <div>
    demo-page
    <p v-if="show">
      现在你看到我了
    </p>
    <button @click="click">
      click
    </button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      show: true,
      num: 3,
    };
  },
  methods: {
    click() {
      console.log(this.$data, '$data');
    },
  },
};
</script>
<style lang="scss">

</style>
