<template>
  <section>
    <button @click="toggleDiv()">{{ showDiv ? 'Hide' : 'Show' }}</button>
    <transition name="fade">
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
$transition-duration: 0.5s;

#container {
  font-family: Inter, Roboto, Oxygen, Fira Sans, Helvetica Neue, sans-serif;
  margin-top: 20px;
  line-height: 22px;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
  transform: translateY(-20px);
}

.fade-enter-to,
.fade-leave-from {
  opacity: 1;
  transform: translateY(0px);
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity $transition-duration ease-in-out,
    transform $transition-duration ease-in-out;
}
</style>
