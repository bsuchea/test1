
<template>
  <div style="font-size: 25px;">
    <input v-model="student" type="text" style="font-size: 25px;">
    <button @click="add">Add</button>
  </div>
  <div v-if="check">
    <h2>Book List</h2>
    <ul>
      <li v-for="ret in books">{{ ret }}</li>
    </ul>
  </div>
  <div v-else-if="!check&books.length>3">
     Read More
  </div>
  <div v-else>
      <h2>Computer List</h2>
      <ul>
        <li v-for="ret in computers">{{ ret }}</li>
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
      console.log(this.student);
    }
  }
}
</script>
