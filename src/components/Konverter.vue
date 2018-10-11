<template>
  <div>
    <h1>Kaalu teisendamine</h1>
    <h4>Sisesta kaal kilogrammides:</h4>
    <input type="number" min="0" v-model="kg">
    <table v-if="kg !== ''">
      <tr>
        <td>Grammid</td>
        <td class="right">{{ convertKg(1000) + ' g' }}</td>
      </tr>
      <tr>
        <td>Naelad</td>
        <td class="right">{{ convertKg(2.20462262) + ' lb' }}</td>
      </tr>
      <tr>
        <td>Untsid</td>
        <td class="right">{{ convertKg(35.2739619) + ' oz' }}</td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: 'Konverter',
  data () {
    return {
       kg: ''
    }
  },
  methods: {
    convertKg(multiplier) { 
      return (this.kg !== 0) ? (this.kg * multiplier).toFixed(2) : 0
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  div {
    text-align: center;
    padding: 0;
	box-sizing: border-box;
	font-family: 'Montserrat', sans-serif;
    margin-top: 25vh;
  }
  table {
    margin-left: auto;
    margin-right: auto;
    text-align: left;
    font-weight: bolder; 
  }
  td {
    padding-top: 7px;
  }
  .right {
    text-align: right;
    padding-left: 20px;
  }
</style>
