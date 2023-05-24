<script>
import headerVue from './components/header.vue';
import yugiohListVue from './components/yugiohList.vue';
import filterVue from './components/filter.vue';
import axios from 'axios';
import { store } from './store'
export default {
  data() {
    return {
      store,
    };
  },
  components: {
    headerVue,
    yugiohListVue,
    filterVue
  },
  methods: {
    requestDataFromApi() {
      axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0", {
        params: {
          archetype: this.store.searchArchetype,
        },
      }).then((response) => (this.store.cardList = response.data.data));
    },
  },
  created() {
    // qui fare la richiesta all'api
    axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0").then(response => { console.log(response); (this.store.cardList = response.data.data) });
    axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php').then(response => (this.store.archetypesList) = response.data);
  },
}
</script>

<template>
  <headerVue />
  <main>
    <div class="container">
      <filterVue @performSearch="requestDataFromApi" />
      <div class="small_container">
        <yugiohListVue />
      </div>
      <div class="found-cards">Found {{ store.cardList.length }} Cards</div>
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
}

.container {
  max-width: 1000px;
  margin: 0 auto;
  padding: 1rem;
}

.small_container {
  display: flex;
  flex-wrap: wrap;
}
</style>
