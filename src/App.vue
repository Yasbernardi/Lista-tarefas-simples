<template>
  <section>
    <cabecalho :valor="titulo" />
    <div class="container">
      <adicionar-tarefa @adicionarTarefa="adicionarTarefa" />
      <listar-tarefas :tarefas="tarefas" />
      <footer>
        <em>Altere aqui o título da sua lista de tarefas</em>
        <entrada-dados v-model="titulo" type="text" />
      </footer>
    </div>
    <rodape />
  </section>
</template>

<script>
import cabecalho from "@/components/cabecalho";
import Rodape from "@/components/Rodape";
import ListarTarefas from "@/components/ListarTarefas";
import AdicionarTarefa from "@/components/AdicionarTarefa";
import EntradaDados from "@/components/templates/EntradaDados";
export default {
  name: "App",
  components: {
    cabecalho,
    Rodape,
    ListarTarefas,
    AdicionarTarefa,
    EntradaDados,
  },
  data() {
    return {
      titulo: "Minha lista de tarefas",
      tarefas: [
        { titulo: "Estudos", checked: true },
        { titulo: "Programar lista de tarefas", checked: true },
      ],
    };
  },
  methods: {
    adicionarTarefa(novaTarefa) {
      this.tarefas.push({
        titulo: novaTarefa,
        checked: false,
      });
    },
  },
};
</script>

<style>
.container {
  width: 60%;
  margin: 20px auto 0px auto;
}
ul li {
  list-style: none;
  padding: 3px;
  background: #8E24AD;
}
.removed {
  color:#8E24AD;
  background: #FAEBFF;
}
.removed label {
  text-decoration: line-through;
}
</style> 