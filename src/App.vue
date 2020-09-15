<template>
  <body id="app">
    <section class="periodic">
      {{info}}
    </section>
  </body>
</template>

<script>
import axios from 'axios';
export default {
  name: 'App',


  el: '#app',
  data () {
    return {
      info: null
    }
  },
  mounted () {
    axios
      // .get('https://api.coindesk.com/v1/bpi/currentprice.json')
      .get('https://raw.githubusercontent.com/Bowserinator/Periodic-Table-JSON/master/PeriodicTableJSON.json')
      .then(response => (this.info = response))
  }
}
</script>