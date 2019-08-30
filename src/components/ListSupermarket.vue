<template>
  

   <table id="tblSupplier" class="table">

      
      <tbody v-for="supermarket in supermarkets" :key="supermarket.SUPERMARKETID">
          <tr>
              <td>{{ supermarket.SUPERMARKETID }}</td>
              <td>{{ supermarket.FANTASYNAME }}</td>
               <td class="action">
                <button type="button" name="excluir" @click="deleteSupermarket(supermarket.SUPERMARKETID)">Excluir</button>
            </td>
            
          </tr>
 
      </tbody>
      

    </table>


</template>

<script>

import axios from 'axios';

export default {
  data() {
    return {
      supermarkets: []
    }
  },
  methods: {
    deleteSupermarket(id){
        axios.delete(`http://localhost:3000/supermarket/`+id)
        .then(response => {
          // JSON responses are automatically parsed.
          alert("excluido:"+response.data)
          this.supermarkets = this.getCustomer();
        })
        .catch(e => {
          this.errors.push(e)
        })
     
    },
    getSupermarket(){
          axios.get(`http://localhost:3000/supermarket`)
        .then(response => {
          // JSON responses are automatically parsed.
          this.supermarkets = response.data
        })
        .catch(e => {
          this.errors.push(e)
        })
    }
  },
  
  // Fetches supermarkets when the component is created.
  created() {
    axios.get(`http://localhost:3000/supermarket`)
    .then(response => {
      // JSON responses are automatically parsed.
      this.supermarkets = response.data
    })
    .catch(e => {
      this.errors.push(e)
    })

  }
}
</script>