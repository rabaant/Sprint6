<template>
  <div>
      <div  v-for= "(texto,index) in textosTutorial" 
            v-bind:key="index" class="mx-auto">
           
          <p v-bind:class="{active:index ===Activa}" >{{texto.txt}}</p>
         <img v-bind:class="{show:index ===Activa,hide:index !==Activa}" :src="texto.img" class="background ">
         
      </div>
     
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
    background-color:lightgray;
    opacity:0.8;
}
.active{
    background-color: lightpink;
}
.background{
    height: 100%;
    width: 100%;
    position:absolute;
    top:0;
    left:0;
    z-index: -1;
}
.show{
    display: block;
}

.hide{
    display:none;
}

</style>

