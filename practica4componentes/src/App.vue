<template>
  <div  class ="fondo">
      <navegador/>
        <convertMoneda/>
         <longitud/>
         <almacenamiento/>
         <masa/>
         <tiempo/>
  </div>
</template>

<script>
import Navegador from './components/Navegador.vue';
import convertMoneda from './components/convertMoneda.vue';
import longitud from './components/longitud.vue';
import masa from './components/masa.vue';
import almacenamiento from './components/almacenamiento.vue';
import tiempo from './components/tiempo.vue';


export default {
  name: 'App',
  components: {
   Navegador,
   convertMoneda,
    longitud,
    masa,
    almacenamiento,
    tiempo
  
  }
}
</script>

<style>
.fondo{
  background-image: url('./assets/descarga.jpg');
  height: 200vh;
  
}

</style>
