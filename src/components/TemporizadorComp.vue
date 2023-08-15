<template>
    <div class="is-flex is-align-items-center is-justify-content-space-between">
        <CronometroText :tempoEmSegundos="tempoEmSegundos"/>
        <ButtonIcon :text="'play'" :icon="'play'" :desabilitar="cronometroRodando" @click="iniciar"/>
        <ButtonIcon :text="'stop'" :icon="'stop'" :desabilitar="!cronometroRodando" @click="finalizar"/>
    </div>
</template>

<script lang="ts">
    import { defineComponent } from 'vue';
    import CronometroText from './CronometroText.vue';
    import ButtonIcon from './ButtonIcon.vue';

    export default defineComponent({
    name: 'TemporizadorComp',
    emits: ['aoTemporizadorFinalizado'],
    components: {
        CronometroText,
        ButtonIcon
    },
    data () {
        return {
            tempoEmSegundos: 0,
            cronometro: 0,
            cronometroRodando: false
        }
    },
    methods: {
        iniciar () {
            this.cronometroRodando = true
            this.cronometro = setInterval(() => {
                this.tempoEmSegundos += 1;
            }, 1000)
        },
        finalizar () {
            this.cronometroRodando = false
            clearInterval(this.cronometro)
            this.$emit('aoTemporizadorFinalizado', this.tempoEmSegundos)
            this.tempoEmSegundos = 0
        }
    }
});
</script>

<style scoped>
</style>