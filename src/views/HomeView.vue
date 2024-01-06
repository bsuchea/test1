
<template>
  <div style="font-size: 25px;">
    <input v-model="student" type="text" style="font-size: 25px;">
    <button @click="add">Add</button>
  </div>
  <div>
    <ul>
      <li v-for="ret in studentList">{{ ret }}</li>
    </ul>
  </div>

</template>
<script>
export default{
  data(){
    return {
      check: 0,
      student: '',
      studentList: [],
      books: [
        'javascript', 'vue js', 'c# Programming', 'Database'
      ],
      computers: ['Apple Mac Book', 'Asus', 'Lenovo', 'Dell']
    }
  },
  methods: {
    add(){
      if(this.student.trim() == '' || this.student == undefined) {
        alert('Please insert a student name');
        return;
      }
      this.studentList.push(this.student);
      this.student = '';
    }
  }
}
</script>
