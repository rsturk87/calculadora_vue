<script setup>
import { ref, reactive, computed, onMounted } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Calculadora from './components/Calculadora.vue';
import Resultado from './components/Resultado.vue';

// Estado reativo para os valores da calculadora
const estado = reactive({
  numeroA: 0,
  numeroB: 0,
  operador: '+'
});

// Computed que calcula o resultado sempre que os valores ou o operador mudam
const resultado = computed(() => {
  const a = parseFloat(estado.numeroA);
  const b = parseFloat(estado.numeroB);
  switch (estado.operador) {
    case '+': return a + b;
    case '-': return a - b;
    case '*': return a * b;
    case '/': return b !== 0 ? a / b : 'Erro: Divisão por zero';
    default: return 0;
  }
});

// Funções para atualizar os valores (essas funções serão passadas para o componente Calculadora)
const atualizaNumeroA = valor => {
  estado.numeroA = valor;
};
const atualizaNumeroB = valor => {
  estado.numeroB = valor;
};
const atualizaOperador = valor => {
  estado.operador = valor;
};

// Lógica para alternar o modo escuro
const modoEscuro = ref(false);

const alternarModo = () => {
  modoEscuro.value = !modoEscuro.value;
  document.body.classList.toggle('dark-mode', modoEscuro.value);
  localStorage.setItem('modoEscuro', modoEscuro.value);
};

onMounted(() => {
  const savedMode = localStorage.getItem('modoEscuro');
  if (savedMode === 'true') {
    modoEscuro.value = true;
    document.body.classList.add('dark-mode');
  }
});
</script>

<template>
  <div class="container" :class="modoEscuro ? 'dark-mode' : ''">
    <button @click="alternarModo" class="btn btn modo-toggle">
      {{ modoEscuro ? '🌙 Modo Escuro' : '☀️ Modo Claro' }}
    </button>

    <!-- Cabeçalho simples -->
    <Cabecalho />

    <!-- Componente da Calculadora, recebendo os valores e funções de atualização -->
    <Calculadora 
      :numeroA="estado.numeroA"
      :numeroB="estado.numeroB"
      :operador="estado.operador"
      :atualizaNumeroA="atualizaNumeroA"
      :atualizaNumeroB="atualizaNumeroB"
      :atualizaOperador="atualizaOperador"
    />

    <!-- Componente para exibir o resultado do cálculo -->
    <Resultado :resultado="resultado" />
  </div>
</template>
