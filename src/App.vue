<script>
import headerVue from './components/header.vue';
import yugiohListVue from './components/yugiohList.vue';
import filterVue from './components/filter.vue';
import axios from 'axios';
export default {
  data() {
    return {

    };
  },
  components: {
    headerVue,
    yugiohListVue,
    filterVue
  },
  created() {
    // qui fare la richiesta all'api
    axios

  },
}
</script>

<template>
  <headerVue />
  <main>
    <div class="container">
      <filterVue />
      <yugiohListVue />
    </div>
  </main>
</template>

<style>
* {
  font-family: Inter, system-ui, Avenir, Helvetica, Arial, sans-serif;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

main {
  background-color: #D48F38;
  height: 600px;
}

.container {
  max-width: 1000px;
  margin: 0 auto;
  padding: 1rem;
}
</style>
