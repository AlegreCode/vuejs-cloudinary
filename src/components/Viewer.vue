<script setup>
    const props = defineProps(['urlImage']);
</script>
<template>
    <img :src="props.urlImage" alt="visor" class="img-thumbnail mb-2 mx-auto" />
</template>