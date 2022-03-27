<template>
  <div>
      <div v-if="iniciar===false">
          <h1>Bienvenido a este tutorial</h1>
          <p>Clicando en los botones podrás avanzar o retroceder en las instrucciones</p>
          <p>¿Empezamos?</p>
          <button @click="comenzar" >Comenzar</button>
      </div>
      <div v-if="iniciar===true">
        <BotonsComp v-bind:textButton="Anterior" @clickDone="activeSentence"></BotonsComp>
        <BotonsComp v-bind:textButton="Siguiente" @clickDone="activeSentence"></BotonsComp>
        <EscenaComp v-bind:textosTutorial="textos" v-bind:Activa="currentSentence"></EscenaComp>
      </div>
  </div>
</template>

<script>
import EscenaComp from '@/components/EscenaComp.vue'
import BotonsComp from '@/components/BotonsComp.vue'
import textos2 from '@/assets/js/sentences.js'



export default {
    name:'HomeComp',
    components:{
        EscenaComp,
        BotonsComp
    },
    data(){
        return{
            
            Siguiente:'Següent',
            Anterior:'Anterior',
            currentSentence:0,
            iniciar:false,
            textos:textos2
        }    
    },
    methods:{
        activeSentence(textButton){
            if(textButton == 'Següent'){
                this.currentSentence++
            }else{
                this.currentSentence--
            }
        },
        comenzar(){
            this.iniciar=true
        }
    },
    watch:{
        currentSentence(){
            if(this.currentSentence==4){
                this.currentSentence=0
            }else if(this.currentSentence<0){
                this.currentSentence=3
            }
        }
    },
    
}
</script>

<style>

</style>