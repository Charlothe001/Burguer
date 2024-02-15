<script>
import Modal from "../components/Modal.vue";
export default{
  
  components:{
    Modal
  }
  ,data(){
    return {
      divSelecionada: null,
      mostrarModal: false,
      modalMsg: ""
    }
  }
  ,methods: {    
    
    handleClickSelectBrguer: function(event){
      const divClicada = event.currentTarget;
      const divId = divClicada.id;
      const h3Content = divClicada.querySelector('h3').innerText;
      this.mostrarModal = true;

      this.modalMsg = h3Content;

      if (this.divSelecionada === divId) {
        console.log("A mesma div foi clicada novamente:", divId);
        
      } else {
        console.log("Nova div clicada:", divId);
        this.divSelecionada = divId;

      }
    },
    fecharModal() {
      this.mostrarModal = false;
      // Aqui você pode adicionar lógica adicional ao fechar o modal
    },
    addPedido(){
      console.log("pedido add");
      this.mostrarModal = false;
    }
  }
}


</script>

<template>
  <div class="main_container">
    <div class="main_card">
      <div class="burguer_card">
        <h2>Burgueres</h2>
                
        <div class="card" v-on:click="handleClickSelectBrguer($event)" id="classic">
          <h3>Clássico</h3>
          <p>Pão Ciabata, Salada (alface, tomate, rúcula e cebola), Molho (da casa aioli, barbecue e mostarda), Queijo Prato e Hamburguer Angus Artesanal</p>
          <figcaption>
            <figure></figure>
            <img  alt="img" src="../../public/img/classico.jpg">
          </figcaption>
          <p><strong>R$</strong> 08,00</p>
        </div>

        <div class="card" v-on:click="handleClickSelectBrguer($event)" id="eggBacon">
          <h3>Egg X-Bacon</h3>
          <p>Pão Ciabata, Salada (alface, tomate, rúcula e cebola), Molho (da casa aioli, barbecue e mostarda), Queijo Prato, Ovo, Bacon e Hamburguer Angus</p>
          <figcaption>
            <figure></figure>
            <img alt="img" src="../../public/img/x-egg.jpeg">
          </figcaption>
          <p><strong>R$</strong> 09,50</p>
        </div>

        <div class="card" v-on:click="handleClickSelectBrguer($event)" id="calabresa">        
          <h3>Calabresa</h3>
          <p>Pão Parmesão, Cebola Caramelizada, Molho da Casa Aioli, Queijo Cheddar Fatiado e Hamburguer Angus Artesanal com Calabresa</p>
          <figcaption>
            <figure></figure>
            <img alt="img" src="../../public/img/x-calabresa.jpeg">
          </figcaption>
          <p><strong>R$</strong> 09,90</p>
        </div>
      </div>

      <div class="drink_card">
        <h2>Bebidas</h2>

        <div class="card" v-on:click="handleClickSelectBrguer($event)" id="coca350">
          <h3>Refrigerante em Lata</h3>
          <p>Coca-cola 350ml</p>
          <figcaption>
            <figure></figure>
            <img alt="cola" src="../../public/img/coca-350ml.jpg">
          </figcaption>
          <p><strong>R$</strong> 06,00</p>
        </div>

        <div class="card" v-on:click="handleClickSelectBrguer($event)" id="coca2l">
          <h3>Refrigerante 2 Litros</h3>
          <p>Coca-cola 2lt</p>
          <figcaption>
            <figure></figure>
            <img alt="cola" src="../../public/img/coca-2lt.jpg">
          </figcaption>
          <p><strong>R$</strong> 12,00</p>
        </div>
        
        <div class="card" v-on:click="handleClickSelectBrguer($event)" id="heineken350">
          <h3>Cerveja em Lata</h3>
          <p>Heineken 350ml</p>
          <figcaption>
            <figure></figure>
            <img alt="cola" src="../../public/img/heineken-350ml.jpg">
          </figcaption>
          <p><strong>R$</strong> 08,00</p>
        </div>     

      </div>
      <Modal :mostrarModal="mostrarModal" :addPedido="addPedido" :fecharModal="fecharModal" :msg="modalMsg"/>
      <!--
        <div class="modal" v-if="mostrarModal">
          <div class="modal_content">
            
            <p>Conteúdo do modal aqui...</p>
            <button v-on:click="fecharModal">Fechar</button>
          </div>
        </div>
      -->
    </div>
  </div> 

</template>

<style scoped>
.main_container{
  display: flex;
  flex-direction: column;
  margin: 50px;
  min-height: 485px;
}
.card{
  width: 80%;
  display: flex;
  flex-direction: column;
  margin-bottom: 25px;
  border-left: 4px solid black;
  padding-left: 5px;
}

.card:hover{
  cursor: pointer;
  box-shadow: 2px 2px black;
  background-color: rgb(226, 236, 236);
}

img {
  width: 100px;
  height: 100px;
}


</style>