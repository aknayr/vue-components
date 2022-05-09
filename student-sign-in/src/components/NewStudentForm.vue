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
      if (this.newStudentName && this.newStarID) {
        let student = { name: this.newStudentName, starID: this.newStarID, present: false}
        this.students.push(student)
        this.students.sort (function (student1, student2) {
          return student1.name > student2.name ? 1 : -1
        })
        this.newStudentName = ''
        this.newStarID = ''
        } else {
          this.errors.push ('Name and StarID are required fields.')
        }
      },
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
