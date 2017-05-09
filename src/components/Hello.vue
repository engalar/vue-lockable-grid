<template>

  <div>


    <h1>{{ msg }}</h1>
    <ics-table :columns="gridColumns" :filterKey="searchQuery" :data="gridData"></ics-table>
  </div>
</template>

<script>
  import IcsCell from './Cell'
  import IcsTable from './Table'
//  import kendo from 'kendo'
  export default {
    components: {
      IcsTable,
      IcsCell},
    name: 'hello',
    data () {
      let searchQuery = ''
      let gridColumns = ['name', 'power', 'plan']
      let gridData = [
        {name: 'Chuck Norris', power: Infinity, plan: 38, out: 12},
        {name: 'Bruce Lee', power: 9000},
        {name: 'Jackie Chan', power: 7000},
        {name: 'Jet Li', power: 8000}
      ]
      return {
        msg: 'liuwengao',
        vertical: 'bottom',
        horizontal: 'center',
        duration: 4000,
        edit: false,
        searchQuery: searchQuery,
        gridColumns: gridColumns,
        gridData: gridData
      }
    },
    methods: {
      open () {
//        kendo.alert('hello kendo')
        this.edit = true
      },
      close () {
        this.edit = false
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1, h2 {
    font-weight: normal;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    display: inline-block;
    margin: 0 10px;
  }

  a {
    color: #42b983;
  }
</style>
