<template>

  <section class="src-components-cotizacion">

    <h1>Conversor de temperatura</h1>
    <hr>
    Ingrese temperatura Cº <label for="entrada"></label>
    <input type="number" id="entrada" v-model="entrada">

    <p :style="{color: getColor() }"> Conve temperatura Fº: {{ converToFahrenheit }}</p>
    <p :style="{color: getColor() }"> Conve temperatura Kº: {{ converToKelvin }}</p>
    <br>
    <br>
    <br>


    <h3>RESPUESTAS</h3>
    <p>1: C</p>
    <p>2: B</p>
    <p>3: C</p>
    <p>4: A</p>
    <p>5: C</p>

  </section>

</template>

<script>

export default {
  name: 'src-components-temp',
  props: [],

  data() {
    return {
      entrada : 0
    }
  },
  methods: {

   getColor() {

    console.log(this.entrada)

    let color = '#f54242'

    if(this.entrada <= 0) {
      color = '#429bf5'
    }else if(this.entrada > 0 && this.entrada < 15) {
      color = '#f542ec'
    } else if(this.entrada == 0) {
      color = '#FFFFFF'
    } 
    return color


   }
  
    

  },

  computed: {

    converToFahrenheit() {
      let inpunt = this.entrada
      

      if (inpunt.length == 0) {
        return ''
      }

      return (inpunt * 1.8) + 32
    },

    converToKelvin() {

      let inpunt = this.entrada
      let value = 273.15

      if (inpunt.length == 0) {

        return ''

      }
      let suma = parseFloat(inpunt) + parseFloat(value)

       return suma
    }
  }
}


</script>

<style scoped lang="css">

</style>
