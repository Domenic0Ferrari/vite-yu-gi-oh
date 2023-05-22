<script>
import yugiohCardVue from './yugiohCard.vue';
import { store } from '../store';
export default {
    data() {
        return {
            store,
        };
    },
    components: {
        yugiohCardVue,
    },
};
</script>

<template>
    <yugiohCardVue v-for="character in store.cardList" :key="character.id" :characterData="character" />
</template>

<style scoped></style>
