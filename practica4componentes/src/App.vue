<template>
  <div  class ="fondo">
      <navegador/>
        <convertMoneda/>
         <longitud/>
         <Masa/>
         <Almacenamiento/>
         <Tiempo/>
  </div>
</template>

<script>
import Navegador from './components/Navegador.vue';
import convertMoneda from './components/convertMoneda.vue';
import longitud from './components/longitud.vue';
import Masa from './components/masa.vue';
import Almacenamiento from './components/Almacenamiento.vue';
import Tiempo from './components/Tiempo.vue';


export default {
  name: 'App',
  components: {
   Navegador,
   convertMoneda,
     longitud,
     masa,
     Almacenamiento,
     Tiempo
  
  }
}
</script>

<style>
.fondo{
  background-image: url('./assets/descarga.jpg');
  height: 100vh;
  
}

</style>
