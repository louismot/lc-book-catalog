
<template>
  <div>
<!--    Create a table using theData and define the columns using config-->
    <b-table striped hover sticky-header="720px" :items="theData" :fields="config" style="padding-top: 50px;"></b-table>
  </div>
</template>

<script>


export default {
  name: 'Table',
  props: ['theData', 'config'],
  data() {
    return {

    }
  }
}
</script>