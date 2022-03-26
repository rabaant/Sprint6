<template>
  <div>
      <BotonsComp v-bind:textButton="Anterior" @clickDone="activeSentence"></BotonsComp>
      <BotonsComp v-bind:textButton="Siguiente" @clickDone="activeSentence"></BotonsComp>
      <EscenaComp v-bind:textosTutorial="textos" v-bind:Activa="currentSentence"></EscenaComp>
      
  </div>
</template>

<script>
import EscenaComp from '@/components/EscenaComp.vue'
import BotonsComp from '@/components/BotonsComp.vue'



export default {
    name:'HomeComp',
    components:{
        EscenaComp,
        BotonsComp
    },
    data(){
        return{
             textos:["El nostre heroi estava surant per l'espai sideral quan a la llunyania va albirar una nau espacial",
                "Sentia curiositat per l'interior de la nau i es va posar a inspeccionar-la. Va arribar a una sala amb dues portes.",
                "L'heroi va decidir travessar la porta que el portava a casa",
                "Mentrestant, altres heroes no van tenir tanta sort en la seva elecció ..."
                ],
            Siguiente:'Següent',
            Anterior:'Anterior',
            currentSentence:0
        }    
    },
    methods:{
        activeSentence(textButton){
            if(textButton == 'Següent'){
                this.currentSentence++
            }else{
                this.currentSentence--
            }
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
    }
}
</script>

<style>

</style>