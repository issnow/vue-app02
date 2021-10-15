<template>
  <div>
    <h3>setup</h3>
    <p>num: {{num}}</p>
    <p>num的2倍是:{{twiceNum}}</p>
    <button @click="click">cilck</button>

    <div>
      <span v-for="(e,i) in arr" :key="i">-{{e}}-</span>
    </div>

    <son :num='num'/>
  </div>
</template>

<script>
import {
  onMounted, ref, watch, computed,
} from 'vue';
import son from './02son.vue';

export default {
  components: {
    son,
  },
  setup(prop, context) {
    // *使用ref定义变量
    const num = ref(0);
    const arr = ref([]);
    const setNum = () => {
      // *给变量赋值使用.value语法
      num.value += 2;
    };

    // *setup中使用生命周期钩子函数
    onMounted(() => {
      arr.value = [1, 2, 3, 4, 5];
    });

    // *独立的 computed 属性(计算属性)
    const twiceNum = computed(() => num.value * 2);

    //* watch--侦听器(监听变量的改变) 响应式更改
    watch(num, (newvalue, oldvalue) => {
      console.log(newvalue, 'watch:num');
    });

    //* 这里需要把定义的变量导出,才能用在别的地方
    return {
      arr,
      num,
      setNum,
      twiceNum,
    };
  },
  methods: {
    click() {
      this.setNum();
    },
  },
};
</script>

<style lang="scss" scoped>

</style>
