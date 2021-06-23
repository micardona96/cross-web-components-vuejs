<template>
  <div>
    <button v-if="!send" @click="onClick">Enviar</button>
    <div v-else>Enviado !!!</div>
  </div>
</template>

<script>
import { EventHandler } from "cross-web-components";
const rootEvent = EventHandler.custom("[ROOT]");
export default {
  methods: {
    onClick: () => {
      rootEvent.dispatch(`[CHANGE]`, { date: Date.now() });
    },
  },
  mounted() {
    rootEvent.listener(`[CHANGE_TOO]`, (e) => {
      this.send = e.send;
    });
  },
  data: () => ({
    send: false,
  }),
};
</script>