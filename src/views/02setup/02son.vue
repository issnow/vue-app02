<template>
  <div>

  </div>
</template>

<script>
import { toRefs } from 'vue';

export default {
  props: ['num'],
  setup(props, context) {
    const { num } = toRefs(props);
    console.log(num.value, 'num');
  },
};
</script>

<style lang="scss" scoped>

</style>
