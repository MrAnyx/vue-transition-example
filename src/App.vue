<template>
  <section>
    <button @click="toggleDiv()">{{ showDiv ? 'Hide' : 'Show' }}</button>
    <transition name="expand">
      <div id="container" v-show="showDiv">
        Modi ipsam facere repellendus et rerum laudantium repellendus sint.
        Ratione iusto saepe pariatur amet reprehenderit atque. Sit excepturi
      </div>
    </transition>
  </section>
</template>

<script>
import { defineComponent } from 'vue';
export default defineComponent({
  data() {
    return {
      showDiv: false,
    };
  },
  methods: {
    toggleDiv() {
      this.showDiv = !this.showDiv;
    },
  },
});
</script>

<style lang="scss">
#container {
  font-family: Inter, Roboto, Oxygen, Fira Sans, Helvetica Neue, sans-serif;
  margin-top: 20px;
  line-height: 22px;
}

.expand-enter-from,
.expand-leave-to {
  opacity: 0;
  transform: translateY(-20px);
}

.expand-enter-to,
.expand-leave-from {
  opacity: 1;
  transform: translateY(0px);
}

.expand-enter-active,
.expand-leave-active {
  transition: opacity 0.4s ease-in-out, transform 0.4s ease-in-out;
}
</style>
