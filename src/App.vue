<template>
  <div id="app">

    <h1>Conversor de Moedas</h1>

    <div class="row">
      <Converter currency-from="USD" currency-to="BRL"/>
      <Converter currency-from="BRL" currency-to="USD"/>
    </div>
    <div class="row">
      <Converter currency-from="CAD" currency-to="BRL"/>
      <Converter currency-from="BRL" currency-to="CAD"/>
    </div>
    <div class="row">
      <Converter currency-from="EUR" currency-to="BRL"/>
      <Converter currency-from="BRL" currency-to="EUR"/>
    </div>
  </div>
</template>

<script>
import Converter from "./components/Converter.vue";

export default {
  name: "app",
  components: { Converter },
  data(){
    return {
      numbers: [1,2,3]
    }
  }
};

</script>

<style>
#app {
  max-width: 900px;
  margin: auto;
  font-size: 0.6em;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smotthing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
.row {
  display: flex;
  justify-content: space-between;
}
h1 {
  text-align: center;
}
</style>
