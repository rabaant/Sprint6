<template>
  <button @click="clicar">{{textButton}}</button>
</template>

<script>
export default {
    name:'BotonsComp',
    props:['textButton','currentSentence'],
    methods:{
        clicar(){
            this.$emit('clickDone',this.textButton);
            
        }
    }
   

}
</script>

<style>
button{
    padding: 5px;
    width: 45%;
    height: 5rem;
}
</style>