<template>
  <div class="conteiner">
    <div>
      <h1>Conversão de Moedas</h1>
    </div>
    <div class="input-cotacao">
      <span class="p-float-label">
          <InputText  id="input-reais" type="text" v-model="reais"/>
          <label for="input-reais">Valor em Reais</label>
      </span>
    </div>
    <div class="input-cotacao">
      <span class="p-float-label">
        <InputText  id="input-cotacao" type="text" v-model="cotacao"/>
        <label for="input-cotacao"> Cotação </label>
        </span>
    </div>
    <div class="buttons" v-if="cotacao" >
      <Button label="Calcular" @click="calcular" class="p-button-rounded"/>
      <Button label="Limpar" @click="limpar" class="button-calcular p-button-rounded"/>
    </div>

    <div>
      <p v-if="resultado"> O valor em Dólares é: US$ {{resultado}}</p>
    </div>
  </div>
  
</template>

<script>

export default {
  data(){
    return{
      reais: null,
      cotacao: null, 
      resultado: null
    }
  },
  methods:{
    calcular(){
      this.resultado = (this.reais / this.cotacao).toFixed(2) ;
    },

    limpar(){
       this.reais = null,
      this.cotacao = null, 
     this.resultado= null
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  
}
h1{
  font-size: 25px;
  text-align: center;
  color: black;
  text-shadow: 1px 1px purple;
}
p{
  text-align: center;
  margin-top: 2rem;
  margin-left: 60px;
  margin-right: 60px;
  padding: 3px;
  border-radius: 10px;
  color: white;
  background-color: purple;
  
}
.input-cotacao{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-top: 2rem;
  
  
}
.buttons{
  margin-top: 2rem;
   display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}
.button-calcular{
  margin-left: 2rem !important; 
}
.conteiner{
  margin: auto;
  height: 400px;
  width: 400px;
  border: 2px solid purple;
  border-radius: 3rem;
}

</style>