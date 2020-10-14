<template>
  <div>
    <b-navbar class="header" fixed="top" type="dark" variant="dark" >
      <b-navbar-brand href="#">Miss. Criden's Reading Catalog</b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav class="ml-5">
          <b-button-group>
            <b-button v-b-modal.select-teacher style="background-color: #904bc9; border-color: white; ">Teacher Select</b-button>
            <b-button v-b-modal.signout-book style="background-color: #904bc9; border-color: white">Book Sign Out Form</b-button>
          </b-button-group>
<!--    This is the form for signing out a book      -->
          <b-modal id="signout-book" title="Sign Out" ok-title="Enter">
            <b-form-input v-model="bookTitle" placeholder="Enter The Book's Title:"></b-form-input>
            <b-form-input v-model="bookAuthor" placeholder="Enter The Author's Name:"></b-form-input>
            <b-form-input v-model="bookDate" placeholder="Enter Today's Date:"></b-form-input>
            <b-form-input v-model="studentName" placeholder="Enter Your First and Last Name:"></b-form-input>
          </b-modal>
<!--    This form allows a student to select who their teacher is to change the catalog      -->
          <b-modal id="select-teacher" title="Select Your Teacher" ok-title="Enter">
            <b-form-select v-model="selected" :options="options"></b-form-select>
            <div class="mt-3">Selected: <strong>{{ selected }}</strong></div>
          </b-modal>
        </b-navbar-nav>
<!--    Search bar    -->
        <b-navbar-nav class="ml-auto">
          <!-- <b-nav-form>-->
            <!-- <b-form-input size="sm" class="mr-sm-2" placeholder="Search"></b-form-input>-->
           <!--  <b-button size="sm" class="my-2 my-sm-0" type="submit">Search</b-button>-->
          <!-- </b-nav-form>-->

          <b-nav-item-dropdown right>
<!--        Button for teacher login-->
            <template v-slot:button-content>
              <em>Teachers</em>
            </template>

<!--        Teacher login prompt    -->
            <b-dropdown-item v-b-modal.login-prompt>Sign In</b-dropdown-item>
            <b-modal id="login-prompt" title="Teacher Login" ok-title="Enter">
              <b-form-input v-model="username" placeholder="Enter Username:"></b-form-input>
              <b-form-input v-model="password" placeholder="Enter Password:"></b-form-input>
              <div class="mt-2">Value: {{ username }}</div>
            </b-modal>
          </b-nav-item-dropdown>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {
      username: '',
      password: '',
      bookTitle: '',
      bookAuthor: '',
      bookDate: '',
      studentName: '',
      selected: null,
      options: [
        { value: null, text: 'Click to select a teacher...' },
        { value: 'a', text: 'Miss Criden' },
        { value: 'b', text: 'second teacher' },
      ]
    }
  }
}
</script>

<style scoped>

/*change color of navbar to country parkway purple*/
.navbar.navbar-dark.bg-dark{
  background-color: #580078!important;
}



</style>