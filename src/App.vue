<script setup lang="ts">
import { Buffer } from "buffer";
globalThis.Buffer = Buffer;

import HelloWorld from "./components/HelloWorld.vue";

console.log("process.env\u200b.NODE_ENV:", process.env.NODE_ENV);
</script>

<template>
  <HelloWorld msg="Hello Vue 3 + TypeScript + Vite" />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
