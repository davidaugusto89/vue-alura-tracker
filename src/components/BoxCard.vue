<template>
    <div class="box has-text-weight-bold">
        <slot></slot>
    </div>
</template>

<script lang="ts">
    import { defineComponent, PropType } from 'vue';

    export default defineComponent({
    name: 'BoxCard',
    data () {
        return {
        }
    }
});
</script>

<style scoped>
.box{
    background: #FAF0CA;
}
</style>