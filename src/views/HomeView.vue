
<template>
  <div>
    <input v-model="student" type="text" class="px-4 py-2 rounded text-md border border-neutral-400">
    <button @click="add" class="px-4 py-2 mx-1 rounded text-md border border-neutral-400 hover:bg-cyan-700 hover:text-gray-200">Add</button>
  </div>
  <div>
    Student List ({{ studentList.length }})
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
      studentList: []
    }
  },
  methods: {
    add(){
      if(this.student.trim() == '' || this.student == undefined) {
        alert('Please insert a student name');
        return;
      }
      this.studentList.push(this.studen);
      this.student = '';
    }
  }
}
</script>
