<template>
  <div>
    provide-inject
    <son />
  </div>
</template>
<script>
import son from './02son.vue';

export default {
  components: {
    son,
  },
  provide: {
    name: 'guocheng',
  },
};
</script>
<style lang="">

</style>
