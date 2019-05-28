<template>
<div id="app">
  <nav class="navbar navbar-dark bg-success mb-4">
    <span class="navbar-brand mb-0 h1">IPTU Verde Chapecó</span>
  </nav>
  <div class="container">
    <div class="row">
      <div class="col-sm-4 mb-4">
        <img id="imagem-arvore" src="src\assets\arvore.png" class="card-img-top">
      </div>
      <div class="col-sm-8">
        <h5>O que é? <span class="badge badge-success">Sobre</span></h5>
        <div id="sobre">
          <p align="justify">O Selo IPTU Verde Chapecó é uma certificação ambiental que tem como 
            principal objetivo reconhecer e premiar ações que demonstrem contribuições 
            na preservação e otimização do uso dos recursos naturais na cidade de Chapecó. </p>
          <p align="justify">Em troca a Prefeitura Municipal de Chapecó vai proporcionar benefício tributário no 
            pagamento do Imposto Predial e Territorial Urbano / IPTU e proporcionar ao beneficiário 
            utilizar a logomarca de aquisição do selo que terá validade de dois anos. </p>
          <p align="justify">Pode ser aplicada para <b>residências, edifícios comerciais e serviços, condomínio de apartamentos, 
            condomínios horizontais e a quadras e lotes urbanos vazios.</b></p>
            <router-link to="Cadastro_Usuario">
              <button type="button" class="btn btn-primary btn-sm">Agendar Vistoria</button>
            </router-link>
            
            <button type="button" class="btn btn-danger btn-sm" v-b-modal="'modal-pontuacao'">Pontuação</button>
            <button type="button" class="btn btn-success btn-sm">Simule Aqui</button>
            
        </div>
        <br>
      </div>

      <b-modal id="modal-pontuacao" centered hide-footer title="Pontuação">
        <div class="mt-1 col-sm-12">
          <div class="card" style="width: 10rem;">
            <img src="src\assets\bronze.png" class="card-img-top" alt="...">
            <div class="card-body">
              <h5 id="h5_medalhas" class="card-text">Medalha de Bronze</h5>
              <button type="button" class="btn btn-dark btn-lg btn-block">10%</button>
            </div>
          </div>
        </div>
        <div class="mt-1 col-sm-12">
          <div class="card" style="width: 10rem;">
            <img src="src\assets\prata.png" class="card-img-top" alt="...">
            <div class="card-body">
              <h5 id="h5_medalhas" class="card-text">Medalha de Prata</h5>
              <button type="button" class="btn btn-secondary btn-lg btn-block">15%</button>
            </div>
          </div>
        </div>
        <div class="mt-1">
          <div class="card" style="width: 10rem;">
            <img src="src\assets\ouro.png" class="card-img-top" alt="...">
            <div class="card-body">
              <h5 id="h5_medalhas" class="card-text">Medalha de Ouro</h5>
              <button type="button" class="btn btn-warning btn-lg btn-block">20%</button>
            </div>
          </div>
        </div>
        <div class="mt-1">
          <div class="card" style="width: 10rem;">
            <img src="src\assets\diamante.png" class="card-img-top" alt="...">
            <div class="card-body">
              <h5 id="h5_medalhas" class="card-text">Medalha de Diamante</h5>
              <button type="button" class="btn btn-success btn-lg btn-block">80%</button>
            </div>
          </div>
        </div>
      </b-modal>

      
    </div>
  </div>    
</div>

</template>

<script>
const firebase = require('firebase/app');
import { contasRef, movimentosRef } from './firebase';
import { sum, subtract, isEmpty} from 'lodash';

  export default{
    data() {
      return {
        show: true,
      }
    },

    firebase: {
      contas: contasRef,
      movimentos: movimentosRef
    },
  
    methods:{
    }
  }
</script>

<style>
#sobre {
  text-align: center;
  color: grey;
}
#h5_medalhas {
  text-align: center;
}

</style>
