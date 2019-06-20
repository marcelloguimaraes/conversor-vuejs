<template>
  <div class="converter">
    <h2>{{currencyFrom}} para {{currencyTo}}</h2>
    <input type="text" v-model="currencyFromValue" v-bind:placeholder="currencyFrom">
    <input type="button" v-on:click="convertCurrency()" value="Converter">
    <h2>{{currencyToValue}}</h2>
  </div>
</template>

<script>
export default {
  name: "Converter",
  props: ["currencyFrom", "currencyTo"],

  data() {
    return {
      currencyFromValue: "",
      currencyToValue: 0
    };
  },
  methods: {
    convertCurrency() {
      const API_KEY = "e40a86862b482172ae86";
      const FROM_TO = `${this.currencyFrom}_${this.currencyTo}`;
      let url = `
				https://free.currencyconverterapi.com/api/v5/convert?q=${FROM_TO}&compact=y&apiKey=${API_KEY}
			`;

      fetch(url)
        .then(res => res.json())
        .then(data => {
          let quote = data[FROM_TO].val;
          this.currencyToValue = (
            quote * parseFloat(this.currencyFromValue)
          ).toFixed(2);
        });
    }
  }
};
</script>

<style scoped>
.converter {
  margin-top: 20px;
  padding: 40px;
  max-width: 300px;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
}
</style>
