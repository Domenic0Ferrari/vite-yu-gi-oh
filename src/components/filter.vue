<script>
import { store } from '../store';
export default {
    data() {
        return {
            store,
        };
    },
}
</script>


<template>
    <select name="card" id="style_card" v-model="store.arrSelect">
        <option v-for="option in store.archetypesList">{{ option.archetype_name }}</option>
    </select>
</template>

<style scoped>
select {
    margin: 2rem 0;
}
</style>
