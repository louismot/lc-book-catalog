<template>
  <div id="app">

    <Table v-if="tableData" :theData = "tableData" :config="config"/>
    <Navbar/>
  </div>
</template>

<script>
 import Table from "./components/Table";
 import Navbar from "./components/Navbar";

export default {
  name: 'App',
  components: {
    Table,
    Navbar
  },
  data: () => ({
    tableData: undefined,
    config:[
      {
        key: 'Level',
        title: 'Level',
        sortable: true

      },
      {
        key: 'Title',
        title: 'Title',
        sortable: true

      },
      {
        key: 'Author',
        title: 'Author',
        sortable: true
      },
      {
        key: 'Available',
        title: 'Available',
        sortable: true
      }
    ]
  }),
  mounted () {
    this.$axios.get('https://5f57dab31a07d600167e765c.mockapi.io/test/books')
    .then(({data}) => {
      this.tableData = data
    })
  }
}
</script>

<style>
#app {

}
</style>
