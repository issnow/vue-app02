<template>
  <div>
    <div>rxjs学习</div>
    <button id="btn" ref="btn">button click</button>
  </div>
</template>

<script>
import { fromEvent, Observable } from 'rxjs';
import { scan, throttleTime, map } from 'rxjs/operators';

export default {
  data() {
    return {
      value: 1,
    };
  },
  mounted() {
    const { btn } = this.$refs;
    // fromEvent(btn, 'click').subscribe(() => {
    //   console.log('11111111');
    // });

    // fromEvent(btn, 'click')
    //   .pipe(scan((n) => n + 1, 0))
    //   .subscribe((n) => console.log(`click${n}times`));

    // fromEvent(document, 'click').pipe(
    //   throttleTime(1000),
    //   scan((v) => v + 1, 0),
    // ).subscribe((n) => console.log(`click${n}times`));

    // let count = 0;
    // const rate = 1000;
    // let lastClick = Date.now() - rate;
    // document.addEventListener('click', (event) => {
    //   if (Date.now() - lastClick >= rate) {
    //     count += event.clientX;
    //     console.log(count);
    //     lastClick = Date.now();
    //   }
    // });

    // fromEvent(document, 'click')
    //   .pipe(
    //     throttleTime(1000),
    //     map((e) => e.clientX),
    //     scan((count, clientX) => count + clientX, 0),
    //   ).subscribe((e) => console.log(`click${e}`));

    const foo = new Observable((subscribe) => {
      console.log('hello');
      subscribe.next(42);
      subscribe.next(60);
      subscribe.next(80);
    });
    foo.subscribe((x) => {
      console.log(x);
    });
  },
};
</script>

<style lang="scss" scoped>

</style>
