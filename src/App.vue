<template>
  <div>
    <h1>{{ title }}</h1>

    <input v-model="message" placeholder="Ketik pesan di sini" />

    <button @click="showMessage">Tampilkan Pesan</button>

    <p v-if="isMessageVisible">{{ message }}</p>

    <p :class="{ 'highlight': isHighlighted }">Ini adalah teks dengan attribute binding.</p>

    <button @click="toggleHighlight">Toggle Highlight</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const title = ref('Selamat Datang di Proyek Vue dengan Vite!');
const message = ref('');
const isMessageVisible = ref(false);
const isHighlighted = ref(false);

function showMessage() {
  isMessageVisible.value = true;
}

function toggleHighlight() {
  isHighlighted.value = !isHighlighted.value;
}
</script>

<style>
.highlight {
  color: red;
  font-weight: bold;
}
</style>
