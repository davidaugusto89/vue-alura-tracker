<template>
    <section>
        <strong class="display">{{ tempoDecorrido }}</strong>
    </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'CronometroText',
  props: {
    tempoEmSegundos: {
        type: Number,
        default: 0
    }
  },
  data () {
    return {
    }
  },
  computed: {
    tempoDecorrido (): string {
        return new Date(this.tempoEmSegundos * 1000).toISOString().substr(11,8);
    }
  },
  methods: {
  }
});
</script>

<style>
.display {
  background-color: var(--bg-primario);
  color: var(--texto-primario);
}

</style>