<script setup>
const props = defineProps([
    'numeroA',
    'numeroB',
    'operador',
    'atualizaNumeroA',
    'atualizaNumeroB',
    'atualizaOperador'
]);
</script>

<template>
    <div class="calculadora">
        <div class="row">
            <!-- Campo para o Número A -->
            <div class="col">
                <input type="number" :value="numeroA" @input="props.atualizaNumeroA($event.target.value)"
                    class="form-control" placeholder="Número A" />
            </div>

            <!-- Select para escolher a Operação -->
            <div class="col">
                <select :value="operador" @change="props.atualizaOperador($event.target.value)" class="form-control">
                    <option value="+">+</option>
                    <option value="-">-</option>
                    <option value="*">*</option>
                    <option value="/">/</option>
                </select>
            </div>

            <!-- Campo para o Número B -->
            <div class="col">
                <input type="number" :value="numeroB" @input="props.atualizaNumeroB($event.target.value)"
                    class="form-control" placeholder="Número B" />
            </div>
        </div>
    </div>
</template>