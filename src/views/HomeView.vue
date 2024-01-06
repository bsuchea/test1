
<template>
  <div v-for="(ret, index) in books" :key="ret.Id" class="book">
    <div>{{ ret.Name }} ({{ ret.Description }})</div>
  </div>
</template>
<script>
export default{
  data(){
    return {
      books: [
        {Id: 1, Name: "Javascript" , Description: "Learn More do more with Javascript"},
        {Id: 2, Name: "Java Programming" , Description: "basic Java Programming start from scratch"},
        {Id: 3, Name: "C# Programming" , Description: ""},
      ],
      assigments: []
    }
  }
}
</script>
<style>
.book{
  font-size:18px;
}
</style>
