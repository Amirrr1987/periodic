<template>
  <body id="app">
    <ul v-for="(info, index) in infos" :key="index">
      <li v-for="(item, key) in info" :key="key">{{key}}: {{item.name}}</li>
      <li v-for="(item, key) in info" :key="key">{{key}}: {{item.appearance}}</li>
      <li v-for="(item, key) in info" :key="key">{{key}}: {{item.atomic_mass}}</li>
      <li v-for="(item, key) in info" :key="key">{{key}}: {{item.boil}}</li>
      <li v-for="(item, key) in info" :key="key">{{key}}: {{item.category}}</li>
      <li v-for="(item, key) in info" :key="key">{{key}}: {{item.color}}</li>
      <li v-for="(item, key) in info" :key="key">{{key}}: {{item.density}}</li>
      <li v-for="(item, key) in info" :key="key">{{key}}: {{item.discovered_by}}</li>
      <li v-for="(item, key) in info" :key="key">{{key}}: {{item.melt}}</li>
      <li v-for="(item, key) in info" :key="key">{{key}}: {{item.molar_heat}}</li>
      <li v-for="(item, key) in info" :key="key">{{key}}: {{item.named_by}}</li>
      <li v-for="(item, key) in info" :key="key">{{key}}: {{item.number}}</li>
      <li v-for="(item, key) in info" :key="key">{{key}}: {{item.period}}</li>
      <li v-for="(item, key) in info" :key="key">{{key}}: {{item.phase}}</li>
      <li v-for="(item, key) in info" :key="key">{{key}}: {{item.source}}</li>
      <li v-for="(item, key) in info" :key="key">{{key}}: {{item.spectral_img}}</li>
    </ul>
  </body>
</template>

<script>
import axios from 'axios';
export default {
  name: 'App',


  // el: '#app',
  data () {
    return {
      infos: null,
// items: [
//       { message: 'Foo' },
//       { message: 'Bar' }
//     ]
    }
  },
  mounted () {
    axios
      // .get('https://api.coindesk.com/v1/bpi/currentprice.json')
      .get('https://raw.githubusercontent.com/Bowserinator/Periodic-Table-JSON/master/PeriodicTableJSON.json')
      
      .then(response => (this.infos = response.data))
      // console.log(this.info);
    
  }
  
}

</script>