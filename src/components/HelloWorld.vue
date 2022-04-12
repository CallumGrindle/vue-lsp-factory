<script setup lang="ts">
import { LSPFactory } from "@lukso/lsp-factory.js";

const deploy = async () => {
  const { ethereum } = window as any;
  const accounts = await ethereum.request({
    method: "eth_requestAccounts",
    params: [],
  });

  const lspFactory = new LSPFactory(ethereum);

  console.log("deploying");

  const myLSP4Data = {
    description: "My Digital Asset",
    links: [{ title: "LUKSO Docs", url: "https://docs.lukso.tech" }],
  };

  const digitalAsset = await lspFactory.LSP7DigitalAsset.deploy({
    controllerAddress: "0xb74a88C43BCf691bd7A851f6603cb1868f6fc147",
    isNFT: true,
    name: "HWG",
    symbol: "HWG",
  });

  console.log(digitalAsset);
};
</script>

<template>
  <button v-on:click="deploy">Deploy</button>
</template>

<style scoped>
a {
  color: #42b983;
}

label {
  margin: 0 0.5em;
  font-weight: bold;
}

code {
  background-color: #eee;
  padding: 2px 4px;
  border-radius: 4px;
  color: #304455;
}
</style>
