<script>
import { store } from '../store';
export default {
    data() {
        return {
            store,
        };
    },
    methods: {
        emitSearchEvent() {
            this.$emit("performSearch");
        },
    },
}
</script>


<template>
    <select name="card" id="style_card" v-model="store.searchArchetype" @change="emitSearchEvent">
        <option value="">Seleziona Archetype</option>
        <option v-for="option in store.archetypesList" :key="option.archetype_name" :value="option.archetype_name">{{
            option.archetype_name }}</option>
    </select>
</template>

<style scoped>
select {
    margin: 2rem 0;
}
</style>
