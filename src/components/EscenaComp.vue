<template>
  <div>
      <div  v-for= "(texto,index) in textosTutorial" 
            v-bind:key="index" class="mx-auto"  
            >
          <p v-bind:class="{active:index ===Activa}">{{texto}}</p>
      </div>
      <!--frase para mostrar en el ej.1
      <p>"El nostre heroi estava surant per l'espai sideral quan a la llunyania va albirar una nau espacial".</p> -->
  </div>
</template>

<script>
export default {
    name:'EscenaComp',
    props:["textosTutorial","Activa"],
     

}
</script>

<style scoped>
p{
    border:2px solid black;
    border-radius: 30px;
    padding:0.5rem;
    margin: 1rem 2rem; 
}
.active{
    background-color: greenyellow;
    
    
}
</style>

