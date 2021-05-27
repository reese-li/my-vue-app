<template>
   <vue-table-dynamic :params="params"></vue-table-dynamic>
   <!-- <div>{{params}}</div> -->
</template>


<script>

import VueTableDynamic from 'vue-table-dynamic'
import axios from 'axios';

export default {

  name: 'Demo',

  data() {
    return {
      params: {
        data: [
            ['code','symbol','rate','description', 'rate_float'],
        ],
        highlight: { row: [1] },
        highlightedColor: 'rgb(243, 235, 200)'
      }
    }
  },

  components: { VueTableDynamic },

  mounted(){
      let self = this
      axios.get('https://api.coindesk.com/v1/bpi/currentprice.json')
        .then(response => 
          Object.values(response.data.bpi).map(
            function (current){
                self.params.data.push(Object.values(current))
          })
        )
        .catch(error => console.log(error) )
        .finally(()=>{}),

      setInterval(()=>{
          let index = this.params.highlight.row.values().next().value;
          console.log(index)
          this.params.highlight= { row: [index%(self.params.data.length-1) +1]};
          index++;
          
      }, 1000)
  }
}

</script>
