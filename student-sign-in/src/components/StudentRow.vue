<template>
    <tr v-bind:class= "{ present: student.present, absent: !student.present }">
        <td> {{ student.name }} </td>
        <td> {{ student.starID }}</td>
        <td> 
        <input type="checkbox" v-bind:checked="student.present" v-on:change="arrivedOrLeft(student, $event.target.checked)"> 
        </td>
    </tr>
    
</template>

<script>
export default {
    name: 'Student Row',
    props: {
        students: Object
    },
    methods: {
        arrivedOrLeft(student, present){
            this.$emit('student-arrived-or-left, student, present')
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .present {
      color: gray;
      font-style: italic;
      background-color: lightgreen;
  }

  .absent {
      color: black;
      font-weight: bold;
      background-color: lightcoral;
  }

  th, tr {
      width: 33%;
  }
</style>
