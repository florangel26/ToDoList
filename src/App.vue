<template>
  <div id="app">
    <h2>Crea una nueva tarea</h2>
    <div class="container formulario">
      <div class="row g-3 align-items-center">
        <div class="col-auto">
          <label for="inputPassword6" class="col-form-label">Tarea</label>
        </div>
        <div class="col-auto">
         <input v-model= "ingresoData" class="form-control" placeholder="Ingrese nueva tarea" type="text" />
        </div>
        <div class="col-auto">
          <button class="btn btn-primary" @click="crearLista()">Crear</button>
        </div>
      </div>
    </div>

    <h2>Lista</h2>
    <ul>
      <li v-for ="(loqsea, index) in lista" :key="index">
       {{ index }}: {{ loqsea }}
      </li>
    </ul>
  </div>
</template>
<script>

export default {
  name: "App",
  data(){
    return{
    ingresoData: "",
    lista: [],
    };
  },
  methods: {
    crearLista(){
      if(this.ingresoData === "") return;
      this.lista.push(this.ingresoData);
      this.ingresoData = "";
      console.log(this.lista);
    }
  },
};
</script>

<style lang="scss">
#app {
  font-family: Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.formulario{
  display: flex;
  justify-content: center;
}
h2{
  margin: 30px 0 30px;
}
label{
  font-weight: bold;
}
</style>
