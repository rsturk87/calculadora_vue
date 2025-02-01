<script setup>
const props = defineProps({
    resultado: {
        type: Number,
        required: true
    }
});
</script>

<template>
    <div class="resultado">
        <h3>Resultado: {{ resultado }}</h3>
    </div>
</template>

<style scoped>
.resultado {
    margin-top: 1rem;
    padding: 1rem;
    border-radius: 4px;
    text-align: center;
}
</style>