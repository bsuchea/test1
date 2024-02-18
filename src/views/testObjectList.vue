<template>
    <h1 class="text-2xl">Test Object List</h1>
    <br>
    Book: <input type="text" class="px-4 py-3 border border-gray-400 rounded" placeholder="book name ">
    <button class="ml-2 px-4 py-3 border border-gray-400 rounded">Add</button>
    <h3 class="text-xl">Book List</h3>
    -------------------
    <div v-if="unReadBooks.length">
        <b>Unread ({{  unReadBooks.length }})</b>
        <p v-for="ret in unReadBooks" :key="ret.id">
            {{ret.id}}- {{ ret.name }} 
            <input type="checkbox" v-model="ret.read">
        </p>
    </div>

    <div v-if="readBooks.length">
        <b>Read ({{ readBooks.length }})</b>
        <p v-for="ret in readBooks" :key="ret.id">
            {{ret.id}}- {{ ret.name }} 
            <input type="checkbox" v-model="ret.read">
        </p>
    </div>

</template>
<script>
export default{
    data() {
        return {
            books: [
                {id: 1, name: 'Java Programming', read: false},
                {id: 2, name: 'C# Programming', read: false},
                {id: 3, name: 'Java Script', read: false},
                {id: 4, name: 'SQL Server', read: false},
            ]
        }
    },
    computed: {
        unReadBooks() {
            return this.books.filter(t =>t.read==false);
        },
        readBooks() {
            return this.books.filter(t =>t.read==true);
        }
    }
}
</script>