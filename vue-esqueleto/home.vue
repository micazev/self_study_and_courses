<template>
  <div>
    <ul>
      <li @click="componenteAtivo = 'PaginaServicos'">Serviços</li>
      <li @click="componenteAtivo = 'PaginaSobre'">Sobre</li>
    </ul>
    <transition mode="out-in">
      <component :is="componenteAtivo"></component>
    </transition>
  </div>
</template>

<script>
import PaginaSobre from "./PaginaSobreEmpresa.vue";
import PaginaServicos from "./PaginaServicos.vue";

export default {
  components: {
    PaginaSobre,
    PaginaServicos
  },
  data() {
    return {
      componenteAtivo: "sobre"
    };
  }
};
</script>

<style>
.v-enter-active,
.v-leave-active {
  transition: all 0.3s;
}

.v-enter,
.v-leave-to {
  opacity: 0;
  transform: translate3d(0, -20px, 0);
}
</style>