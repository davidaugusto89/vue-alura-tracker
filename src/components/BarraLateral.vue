<template>
    <header>
        <h1>
            <img src="../assets/logo.png" alt="" />
        </h1>
        <ButtonIcon icon="circle-half-stroke" :text="textoBotao" @click="alterarTema" />

    </header>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import ButtonIcon from './ButtonIcon.vue';

export default defineComponent({
  name: 'BarraLateral',
  emiits: ['aoTemaAlterado'],
  data () {
    return {
      modoEscuroAtivo: false,
    }
  },
  components: {
    ButtonIcon
  },
  computed: {
    textoBotao() {
      if (this.modoEscuroAtivo) {
        return 'Desativar modo escuro'
      }
      return 'Ativar modo escuro'
    }
  },
  methods: {
    alterarTema() {
      this.modoEscuroAtivo = !this.modoEscuroAtivo;
      this.$emit('aoTemaAlterado', this.modoEscuroAtivo)
    }
  }
});
</script>

<style scoped>
header {
  padding: 1rem;
  background: #101820;
  width: 100%;
  height: 100vh;
  border: none;
  text-align: center;
}
@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
}
</style>