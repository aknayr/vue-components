<template>
  <div class="hello">

      <!-- template here -->
      <div class="alert alert-danger" v-show="errors.length">
              <ul>
                  <li v-for="error in errors" v-bind:key="error">{{ error }}</li>
              </ul>

      </div>

      <div class="card add-student m-2 p-2">
          <h4 class="card-title">Add new student</h4>

          <div class="form-group">
              <label for="name">Name</label>
              <!-- TODO v-model newStudentName -->
              <input id="name" class="form-control" v-model.trim="newStudentName">
          </div>
          <div class="form-group">
              <label for="starID">Star ID</label>
              <!-- TODO v-model newStarID -->
              <input id="starID" class="form-control" v-model.trim="newStarID">
          </div>
          <button class="btn btn-primary" v-on:click="addStudent">Add</button>
      
    </div>
  </div>
  
</template>

<script>
export default {
  // create component here
  name: 'NewStudentForm',
  data () {
    return {
      newStudentName: '',
      newStarID: '',
      errors: []
    }
  },
  methods: {
    addStudent() {
      this.errors = []

      if (!this.newStudentName) 
      {
        this.errors.push('Student Name is a required field.')
      } 
      if (!this.newStarID) 
      {
        this.errors.push('StarID is a required field.')
      }
      if (this.errors.length == 0)
      {
        let student = { name: this.newStudentName, starID: this.newStarID, present:false }
      }
        // TODO emit message to parent with new student info

        this.newStudentName = ''
        this.newStarID = ''
      }
    }
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
