<template>
  <div>
    <h1>Top:{{top}}</h1>
    <div style="position: relative;height: 150px;width: 1000px;overflow: hidden">
      <div id="locked-table" style="vertical-align: top;overflow: hidden; display: inline-block;width: 492px;height: 150px;box-sizing: content-box">
        <ics-table :columns="gridColumns" :filterKey="searchQuery" :data="gridData"></ics-table>
      </div>
      <div id="srollable-table" v-on:scroll="onScroll($event)" style="width: 152px;height: 167px;box-sizing: content-box;display: inline-block;overflow: scroll">
        <ics-table :columns="gridColumns" :filterKey="searchQuery" :data="gridData"></ics-table>
      </div>
    </div>
  </div>

</template>

<script>
  import IcsCell from './Cell'
  import IcsTable from './Table'
  import $ from 'jquery'
  //  import kendo from 'kendo'
  export default {
    components: {
      IcsTable,
      IcsCell
    },
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
        vertical: 'bottom',
        horizontal: 'center',
        duration: 4000,
        edit: false,
        searchQuery: searchQuery,
        gridColumns: gridColumns,
        gridData: gridData,
        top: '-10px'
      }
    },
    methods: {
      open () {
//        kendo.alert('hello kendo')
        this.edit = true
      },
      close () {
        this.edit = false
      },
      onScroll (e) {
        console.log(e.target.scrollTop)
        this.top = $('#srollable-table').scrollTop()
        $('#locked-table').scrollTop($('#srollable-table').scrollTop())
      }
    },
    computed: {
      styles: function () {
        return {
          top: this.top
        }
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
