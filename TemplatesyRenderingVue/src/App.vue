<script >
export default {
  name: 'App', 
  data() {
    return {
      colorDefondo: 'pink',
      colorDetexto: 'black',
      borde : '80',
      tipoDeFigura :"",
      contenidoTexto : "hola",
      tamanosDetexto : 'grande',

      
      textShow: true,
      opaco:"",
      tipografias: ["fantasy","cursive", "serif",]

    };


  },
};
</script>

<template>


  <div id="app">

    <form> 
      <div>
      <label for="colorDefondo">Color de fondo</label>
      <input v-model="colorDefondo">
      </div>

      <div>
      <label for="colorDetexto">Color de texto</label>
      <input v-model="colorDeTexto">
      </div>
      
      <div>
      <span> Mostrar texto <input type="checkbox" v-model="textShow"></span>

      </div>
      <div>
        <label>Borde</label>
        <input type="range" min="0" max="100" v-model="borde"/>
      </div>

      <div>
        <label>Contenido Texto</label>
        <textarea v-model="contenidoTextual"></textarea>
        
      </div>

      <div>
        <label>Tipografia</label>
        <select v-model="tipografia">
          <option value="tipografia" v-for="tipografia in tipografias">
            {{tipografia}}
          </option>
        </select>
      </div>
      <div>
        <label for="opaco"> opaco <input type="checkbox" v-model="opaco"></label>
      </div>

      <div>
        <h3>Tamaño Texto </h3>
     

        <label>Grande</label>
        <input type="radio"
        :name="tamanosDetexto"
        value="500%"
        
       
        v-model="tamanosDetexto"/>



        <label>Mediano</label>
        <input type="radio"
        :name="tamanosDetexto"
        value="300%"
        
        v-model="tamanosDeTexto"/>

        <label>pequeño</label>
        <input type="radio"
        :name="tamanosDetexto"
        value="100%"
        
        v-model="tamanosDetexto"/>


      </div>
    </form>
    </div>
    
    <main>

      <div

       class="figura"
        :style="{
          background: colorDefondo,
          borderRadius: borde + 'px',
          color: colorDeTexto,
          fontFamily: tipografia,
          fontSize:tamanosDetexto ,
        }"

        :class="{opaco}">

        <p v-show="textShow">{{contenidoTextual}}</p>

      </div>
    </main>

</template>


  
  
    
  
  
  


<style scoped>

body {
  margin: 0%;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #3375b7;
  font-display: grid;
  grid-template-columns: 400px 1fr;
  min-height: 100vh;
}
main {
  display: flex;
  justify-content: center;
  align-items: center;

}

.opaco {
  opacity: 0.5;
}
form {
  background: darkslategrey;
  color: white;
  display: flex;
  flex-direction: column;
  padding: 40px;
  gap: 15px;


}
form > div {
  display: grid;
  flex-direction: column;
  text-align: left;
  
  

}

.figura {
 width: 30vw;
 height: 30vw;
 display: grid;
 justify-content: center;
 align-items: center;}
 

</style>
