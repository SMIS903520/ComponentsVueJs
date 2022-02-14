<template>
  <div  class ="fondo">
      <navegador/>
        <convert-moneda/>
         <longitud/>
         <masa/>
         <Almacenamiento/>
         <tiempo/>
  </div>
</template>

<script>
import Navegador from './components/Navegador.vue';
import convertMoneda from './components/convertMoneda.vue';
import longitud from './components/longitud.vue';
import masa from './components/masa.vue';
import Almacenamiento from './components/Almacenamiento.vue';


export default {
  name: 'App',
  components: {
   Navegador,
   convertMoneda,
     longitud,
     masa,
     Almacenamiento,
     tiempo
  
  }
}
</script>

<style>
.fondo{
  background-image: url('./assets/descarga.jpg');
  height: 100vh;
  
}

</style>
