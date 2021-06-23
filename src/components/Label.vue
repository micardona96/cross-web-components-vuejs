<template>
  <pre>{{ name }}</pre>
</template>

<script>
import { EventHandler } from "cross-web-components";
const rootEvent = EventHandler.custom("[ROOT]");
export default {
  mounted() {
    rootEvent.listener(`[CHANGE]`, (e) => {
      this.name = e.date;
      setTimeout(() => {
        rootEvent.dispatch(`[CHANGE_TOO]`, { send: true });
      }, 2000);
    });
  },
  data: () => ({
    name: "",
  }),
};
</script>