<template>
  <div class="input-group">
    <!-- <input @keyup.enter="adicionarTarefa" v-model="novaTarefa" type="text" /> -->
    <!-- <entrada-dados :value="novaTarefa" @input="associarValor" /> -->
    <entrada-dados @salvar="adicionarTarefa" v-model="novaTarefa" />
    <span class="input-group-btn">
      <button @click="adicionarTarefa" class="btn btn-primary">
        Adicionar tarefa
      </button>
    </span>
  </div>
</template>

<script>
import EntradaDados from "@/components/templates/EntradaDados";
export default {
  components: { EntradaDados },
  data() {
    return {
      novaTarefa: "",
    };
  },
  methods: {
    adicionarTarefa() {
      this.$emit("adicionarTarefa", this.novaTarefa);
      this.novaTarefa = "";
    },
  },
};
</script>

<style>
</style>