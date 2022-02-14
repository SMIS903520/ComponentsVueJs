
<template>
  <div>
    <div class="container pt-3">
      <div class="row">
        <div class="col-lg-12">
          <div class="form-group">
              <br>
              <br>
              <!--Aqui es para un texto que aparece e indica lo que hay que hacer-->
             <label for="cantidad">Ingrese los Digitos</label>
             <br>
             <br>
            <input
              class="form-control form-control-lg"
              id="cantidad"
              placeholder="Ingrese cantidad.."
              v-model="cantidad"
              v-on:keyup="onChange"
            />
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col-lg-6">
          <div class="form-group">
              <br>
            <!--Aqui es para un texto que aparece e indica lo que lo que va a convertir-->
            <label for="tengo">Convertir</label>
            <br>
            <br>
            <!--VOY A UTILIZAR LA DIRECTIVA  v-model para los atributos del formulario -->  
            <select
              class="form-control form-control-lg"
              id="tengo"
              v-model="tengo"
              v-on:change="onChange()"
            >
            <!--Aqui es para empezar a indicar que se trabajara con lo que esta dentro de (tiempo)-->
              <option v-for="(tiempo, index) in tiempos" v-bind:key="index">
                {{ tiempo }}
              </option>
            </select>
          </div>
        </div>
        <div class="col-lg-6">
          <div class="form-group">
              <br>
            <label for="quiero">A</label>
            <br>
            <br>
            <!--VOY A UTILIZAR LA DIRECTIVA  v-model para los atributos del formulario -->  
            <select
              class="form-control form-control-lg"  
              id="quiero"
              v-model="quiero"
              v-on:change="onChange()"
            >
              <option v-for="(tiempo, index) in tiempos" v-bind:key="index">
                {{ tiempo }}
              </option>
            </select>
          </div>
        </div>
      </div>
      <div class="text-center pt-4">
        <h6 v-if="cantidad > 0">
          <span class="badge badge-success">{{ cantidad }} {{ tengo }}</span>
          <span class="badge badge-dark"> SON </span>
          <span class="badge badge-success">{{ getTotal(total) }} {{ quiero }}</span>
        </h6>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  data() {
    return {
      //ACA es donde se empieza a hacer la seleccion de lo que va a querer
      tiempos: ["SG (Segundos)", "MIN (Minutos)", "HR (Hora)"],
      cantidad: 0,
      tengo: "SG (Segundos)",
      quiero: "MIN (Minutos)",
      total: 0,
    };
  },
  methods: {
    onChange() {
      switch (this.tengo) {
        // Usuario selecciono que tiene SEGUNDOS
        case "SG (Segundos)":
          if (this.quiero === "SG (Segundos)") {
            this.total = this.cantidad;
          }
          if (this.quiero === "MIN (Minutos)") {
            this.total = this.cantidad / 60.0;
          }
          if (this.quiero === "HR (Hora)") {
            this.total = this.cantidad / 3600.0;
          }
          break;

        // Usuario selecciono que tiene MINUTOS
        case "MIN (Minutos)":
          if (this.quiero === "SG (Segundos)") {
            this.total = this.cantidad * 60.0;
          }
          if (this.quiero === "MIN (Minutos)") {
            this.total = this.cantidad;
          }
          if (this.quiero === "HR (Hora)") {
            this.total = this.cantidad / 60.0;
          }
          break;

          // Usuario selecciono HORA
        case "HR (Hora)":
          if (this.quiero === "SG (Segundos)") {
            this.total = this.cantidad * 3600;
          }
          if (this.quiero === "MIN (Minutos)") {
            this.total = this.cantidad * 60.0;
          }
          if (this.quiero === "HR (Hora)") {
            this.total = this.cantidad;
          }
          break;
        default:
      }
    },
    getTotal(valor) {
        return (valor)
    }
  },
};
</script>


<!--Aca es donde esta la edicion de las letras y color-->
<style scoped>
.badge {
  margin: 2px;
  font-size: 150%;
}
label {
  font-weight: 700;
  font-size: 130%;
  color: black;
  
}
h6{
    color: black;
}
</style>

