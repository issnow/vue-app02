<template>
  <div>
    <p>grandson组件</p>
    name: {{name}}
  </div>
</template>

<script>
export default {
  inject: ['name'],
};
</script>

<style lang="scss" scoped>

</style>
