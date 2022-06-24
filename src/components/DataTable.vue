<template>
  <div>
  <b-row class="tablerow">
    <b-col md="2"></b-col>
    <b-col md="8">
        <b-input v-model="filter" placeholder="Filter table in capital."></b-input>
        <br />
        <b-table 
        bordered 
        striped 
        hover 
        :filter="filter"
        :filter-included-fields="['capital']"
        :items="posts" 
        :fields="fields">
    
        <template #cell(flags)="data">
            <img v-bind:src="data.item.flags.png" />
        </template>

    </b-table>
    </b-col>
  </b-row>

  </div>
</template>

<script>
export default {
  name: 'DataTable',
  data() {
    return {
        fields:[
            'name', {key: 'name', label: 'Name'},
            'capital', {key:'capital', label: 'Capital'},
            'region', {key:'region', label: 'Region'},
            'flags', {key:'flags', label:'Flag'},
        ],
        posts:[],
        items: [],
        filter: '',
    }
  },
  created() {
    fetch('https://restcountries.com/v2/all')
    .then(response =>response.json())
    .then(json => {
        this.posts =json;
    })
  },
}
</script>

<style scoped>
.tablerow{
    margin-top: 50px;
}
</style>