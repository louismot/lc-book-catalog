<template>
  <div class="book-table">
    <table class="table">
      <thead>

      <tr>
        <!--populate headers for each column in the table-->
        <th v-for="(obj, ind) in config" :key="ind">{{ obj.title }}</th>
      </tr>

      </thead>
      <tbody>
      <!--loop through each row, and populate the correct data-->
      <tr v-for="(row, index) in theData" :key="index">
        <td v-for="(obj, ind) in config" :key="ind">{{ row[obj.key]}}</td>
      </tr>

      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "Table",
  props: ['theData', 'config']
}
</script>

<style scoped>

</style>