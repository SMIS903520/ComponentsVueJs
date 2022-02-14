<template>
  <div id="root">
    <div class="contrainer">
      <h1>CONVERSOR DE LONGITUDES</h1>
      <div class="row">
           <div class="col-sm-9">
           <label for="final">Convertir</label>
           <select v-model="final">
           <option value="m">Metro</option>
            <option value="mm">Milímetro</option>
            <option value="cm">Centímetro</option>
            <option value="hm">Hectómetro</option>
            <option value="dm">Decímetro</option>
            <option value="km">Kilómetro</option>
            <option value="dam">Decámetro</option>
            <option value="yd">Yarda</option>
            
        </select>
        </div>
     
       
        </div>
          <div class="col-sm-6">
           <label for="inico">Convertir</label>
           <select v-model="inicio">
           <option value="m">Metro</option>
            <option value="mm">Milímetro</option>
            <option value="cm">Centímetro</option>
            <option value="hm">Hectómetro</option>
            <option value="dm">Decímetro</option>
            <option value="km">Kilómetro</option>
            <option value="dam">Decámetro</option>
            <option value="yd">Yarda</option>
            
         </select>
      </div>
      <div class="row">
         <div class="clo-sm-2 offset-md-4">
            <input type="text" v-model="cantidad" >
         </div>
      </div>
      <br/>
      <div class="row">
           <div class="col-md-9 text-center">
              <button  v-on:click="convertir" class="btn btn-primary">Convertir</button>
           </div>
      </div>
      <div class="row mt-5">
           <div class="col-sm-9 text-center">
             <label>RESULTADO</label>
             <h2>{{calculo}}</h2>
                
             </div>
      </div>
    </div>
  </div>

</template>

<script>
export default{
    name:'Longitud',
    data(){
        return{
            cantidad:"",
            inicio:"m",
            final:"cm",
            valores_log:{
               "m":1,
               "mm":1000,
               "cm":100,
               "hm":0.01,
               "dm":10,
               "km":0.001,
               "dam":0.1,
               "yd":1.0936
            },
            calculo:""
        }
    },
    methods:{
       convertir:function(){
          let inicioL = this.valores_log[this.inicio]
          let finalL = this.valores_log[this.final]
          let verResult =((inicioL/finalL))*this.cantidad

          this.calculo = verResult
       }
    }
}

</script>
