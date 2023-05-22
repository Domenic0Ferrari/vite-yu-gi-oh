<script>
export default {
    props: {
        characterData: Object,
    },
};
</script>

<template>
    <div class="card">
        <img :src="characterData.card_images[0].image_url_small" />
        <h2>{{ characterData.name }}</h2>
        <h3></h3>
    </div>
</template>

<style scoped></style>
