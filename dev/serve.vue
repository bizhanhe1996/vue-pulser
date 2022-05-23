
<template>
  <div id="app">
    <div id="pulser">
      <VuePulser :size="size" :stroke="color" :width="width" :circles="circles" />
    </div>
    <div id="controls">
      <div>Size: <input type="range" min="50" max="250" step="25" v-model="size" /> {{size}}</div>
      <div>Circles: <input type="range" min="1" max="5" step="1" v-model="circles" /> {{circles}}</div>
      <div>Color: <input type="color" v-model="color" /> {{color}}</div>
      <div>width: <input type="range" min="1" max="30" step="1" v-model="width"> {{width}}</div>
    </div>
  </div>
</template>

<script>
import VuePulser from '@/vue-pulser.vue';
export default {
  name: 'ServeDev',
  components: {
    VuePulser
  },
  data() {
    return {
      size: 250,
      circles: 5,
      color: 'red',
      width: 5,
    }
  }
};
</script>

<style>
#controls div {
  padding: 1rem;
  font-family: ubuntu;
}
</style>