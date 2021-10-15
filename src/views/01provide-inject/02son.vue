<template>
  <div>
    son组件
    <grandson />
  </div>
</template>

<script>
import grandson from './03grandson.vue';

export default {
  components: {
    grandson,
  },
};
</script>

<style lang="scss" scoped>

</style>
