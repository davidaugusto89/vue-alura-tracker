<template>
    <button class="button" :disabled="desabilitar">
        <span class="icon">
            <i :class="`fas fa-${icon}`"></i>
        </span>
        <span>{{ text }}</span>
    </button>
</template>


<script lang="ts">
    import { defineComponent } from 'vue';

    export default defineComponent({
    name: 'ButtonIcon',
    props: {
        text: {
            type: String,
            default: '',
        },
        icon: {
            type: String,
            default: '',
        },
        desabilitar: {
            type: Boolean,
            default: false
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