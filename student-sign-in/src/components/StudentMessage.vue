<template>
  <div class="hello">

    <!-- template here -->
    <div v-if="mostRecentStudent.name">

        <div class="alert alert-info" v-if="mostRecentStudent.present">
                Welcome, {{ student.name }}
        </div>

        <div class="alert alert-success" v-else>
                Goodbye, {{ student.name }}. See you later!
        </div>

    </div>
    
  </div>
</template>

<script>
export default {
  // create component here
  name: 'StudentMessage',
  props: {
    student: Object
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
