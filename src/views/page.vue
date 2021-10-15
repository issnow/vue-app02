<template>
  <div>
    demo-page
    <p v-if="show">现在你看到我了</p>

  </div>
</template>
<script>
export default {
  data() {
    return {
      show: true,
    };
  },
};
</script>
<style lang="scss">

</style>
