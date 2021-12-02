<template>
  <div class="input-group">
     <input 
     @keyup.enter="adicionarTarefa" v-model="novaTarefa" type="text"/>
     <span class="input-group-btn">
       <button @click="adicionarTarefa" class="btn btn-light"> Adicionar 
       </button>
     </span>
   </div>
</template>

<script>
export default {
  data () {
    return {
      novaTarefa: "",
    };
  },
  methods: {
    adicionarTarefa() {
      this.$emit("adicionarTarefa", this.novaTarefa);
        this.novaTarefa = "";

    }
  }
};
</script>

<style>

</style>