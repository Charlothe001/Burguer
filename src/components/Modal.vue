<script>
export default{
    name: "Modal",
        

    props: {
        mostrarModal: Boolean,
        fecharModal: Function,
        addPedido: Function,
        msg: String
        
    },
    
}

</script>

<template>

    <div class="modal" v-if="mostrarModal">
        <div class="modal_content">
            
            <h3>{{msg}}</h3>
            <button v-on:click="addPedido">Adicionar</button>
            <button v-on:click="fecharModal">Fechar</button>
          </div>
    </div>

</template>

<style scoped>
    .modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal_content {
  background-color: white;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
}
</style>