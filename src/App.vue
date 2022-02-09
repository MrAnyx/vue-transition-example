<template>
  <section>
    <button @click="toggleDiv()">{{ showDiv ? 'Hide' : 'Show' }}</button>
    <transition name="expand">
      <div id="container" v-show="showDiv">
        Modi ipsam facere repellendus et rerum laudantium repellendus sint.
        Ratione iusto saepe pariatur amet reprehenderit atque. Sit excepturi
        ducimus quam sit sequi nesciunt ratione. Id qui a sequi ut iusto
        suscipit consectetur. Saepe dolores quos ab dolorum sit sit quaerat
        facilis.Rerum autem minus ipsa tempore consequatur. Molestiae ab fugiat
        cupiditate quas in nostrum explicabo et. Minus blanditiis voluptatibus
        quia. Quod ducimus qui numquam. Possimus ut qui sed eos excepturi
        saepe.Natus iusto dolorem est voluptatem. Illum iusto culpa
        necessitatibus iusto exercitationem magni beatae nesciunt. Dolores et
        modi accusantium ipsam tempora. Voluptas beatae asperiores enim
        unde.Consequatur ut rerum nobis et. Voluptas aut aut distinctio
        molestiae odit eum eum quod. Nemo qui veritatis eius est in possimus
        praesentium dolor. Consectetur consectetur aliquid reiciendis odio
        doloremque.Adipisci id voluptatibus explicabo expedita quia. Ut hic
        sapiente commodi delectus dolor. Mollitia a quaerat at molestiae.
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
