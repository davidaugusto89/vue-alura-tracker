<template>
    <BoxCard>
        <div class="columns">
            <div class="column is-7">
                {{  tarefa.descricao || "Tarefa sem descrição" }}
            </div>
            <div class="column">
                <CronometroText :tempoEmSegundos="tarefa.duracaoEmSegundos" />
            </div>
        </div>
    </BoxCard>
</template>

<script lang="ts">
    import { defineComponent, PropType } from 'vue';
    import CronometroText from './CronometroText.vue'
    import BoxCard from './BoxCard.vue'
    import ITarefa from '@/interfaces/ITarefa';

    export default defineComponent({
    name: 'TarefaList',
    components: {
        CronometroText,
        BoxCard
    },
    props :{
        tarefa: {
            type: Object as PropType<ITarefa>,
            required: true
        }
    },
    data () {
        return {
        }
    },
    methods: {
    }
});
</script>

<style scoped>
</style>