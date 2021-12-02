<template>
<section> 
  <cabecalho :valor="titulo"/> 
  <div class="container"> 
   <adicionar-tarefa />
   <listar-tarefas :tarefas="tarefas"/>
   <footer> 
     <em> Altere o título da sua Lista de Tarefas </em> 
     <input 
     v-model="titulo" 
     type="text"/> 
   </footer>
 </div>
<rodape/> 
</section> 
</template>

<script>
import cabecalho from "@/components/cabecalho";
import rodape from "@/components/rodape";
import ListarTarefas from '@/components/ListarTarefas';
import AdicionarTarefa from '@/components/AdicionarTarefa';

export default {
  name: 'App',
  components: { cabecalho, rodape, ListarTarefas, AdicionarTarefa },
  data () { 
    return {
      titulo: "Lista de Tarefas", 
      tarefas: [
        { titulo: "Estudar", checked: false },
        { titulo: "Programar", checked: true },

      ],
    };
  },
  methods : {
    adicionarTarefa() {
      this.tarefas.push( {
        titulo: this.novaTarefa,
        checked: false
      })
    }
  }
};
</script>

<style>

.container {
  width: 40%;
  margin: 20px auto 0px auto;
}
ul li {
  list-style: none; 
}
.removed {
  color: gray;
}

.removed label {
  text-decoration: line-through;
}
</style>

