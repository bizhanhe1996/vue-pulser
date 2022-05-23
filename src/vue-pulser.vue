<template>
  <svg :width="size" :height="size" :viewBox="`0 0 ${size} ${size}`" xmlns="http://www.w3.org/2000/svg">
    <circle :cx="size/2" :cy="size/2" :stroke="color" :stroke-width="width" v-for="begin in nums" :key="begin">
      <animate :begin="begin+'s'" attributeName="r" dur='4s' repeatCount="indefinite" :values="`0;${size/2.5}`" />
      <animate :begin="begin+'s'" attributeName="stroke-opacity" dur='4s' repeatCount="indefinite" values="1;0" />
    </circle>
  </svg>
</template>

<script>
export default {
  name:'VuePulser',
  props: {
    size: Number,
    color: String,
    width: Number,
    duration: Number,
    circles: Number
  },
  computed: {
    nums() {
      let tmp = []
      for (let i = 0; i < this.circles; i++) {
        tmp.push(i)
      }
      return tmp
    }
  }
}
</script>

<style scoped>
circle {
  fill: transparent;
}
</style>