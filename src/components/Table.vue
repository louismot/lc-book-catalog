<!--<template>-->
<!--  <div class="book-table">-->
<!--    <table class="table">-->
<!--      <thead>-->

<!--      <tr>-->
<!--        &lt;!&ndash;populate headers for each column in the table&ndash;&gt;-->
<!--        <th v-for="(obj, ind) in config" :key="ind">{{ obj.title }}</th>-->
<!--      </tr>-->

<!--      </thead>-->
<!--      <tbody>-->
<!--      &lt;!&ndash;loop through each row, and populate the correct data&ndash;&gt;-->
<!--      <tr v-for="(row, index) in theData" :key="index">-->
<!--        <td v-for="(obj, ind) in config" :key="ind">{{ row[obj.key]}}</td>-->
<!--      </tr>-->

<!--      </tbody>-->
<!--    </table>-->
<!--  </div>-->
<!--</template>-->

<!--<script>-->
<!--export default {-->
<!--  name: "Table",-->
<!--  props: ['theData', 'config']-->
<!--}-->
<!--</script>-->

<!--<style scoped>-->

<!--</style>-->

<template>
  <div>
    <b-table striped hover :items="theData" :fields="config"></b-table>
  </div>
</template>

<script>


export default {
  name: 'Table',
  props: ['theData', 'config'],
  data() {
    return {
      items: [
        { age: 40, first_name: 'Dickerson', last_name: 'Macdonald' },
        { age: 21, first_name: 'Larsen', last_name: 'Shaw' },
        { age: 89, first_name: 'Geneva', last_name: 'Wilson' },
        { age: 38, first_name: 'Jami', last_name: 'Carney' }
      ]
    }
  }
}
</script>