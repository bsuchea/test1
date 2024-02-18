<template>
    <h1 class="text-2xl text-blue-500">Student List</h1>

    <div class="mt-2 grid grid-cols-2 gap-x-6 gap-y-8 sm:grid-cols-6">
        <div class="sm:col-span-2">
            <div class="grid grid-cols-1 gap-x-6 gap-y-8 sm:grid-cols-6">
                <div class="sm:col-span-4">
                    <label for="first-name" class="block font-medium leading-6 text-gray-900">Name</label>
                    <div class="mt-2">
                        <input type="text" v-model="student.Name"
                            class="block w-full rounded-md border-0 py-2 px-3 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm sm:leading-6">
                    </div>
                </div>

                <div class="sm:col-span-2">
                    <label for="country" class="block font-medium leading-6 text-gray-900">Gender</label>
                    <div class="mt-2">
                        <select v-model="student.Gender"
                            class="block w-full rounded-md border-0 py-2 px-3 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:max-w-xs sm sm:leading-6">
                            <option value="">--select--</option>
                            <option value="Male">Male</option>
                            <option value="Female">Female</option>
                        </select>
                    </div>
                </div>

                <div class="sm:col-span-3">
                    <label for="email" class="block font-medium leading-6 text-gray-900">Phone</label>
                    <div class="mt-2">
                        <input type="text" v-model="student.Phone"
                            class="block w-full rounded-md border-0 py-2 px-3 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm sm:leading-6">
                    </div>
                </div>

                <div class="sm:col-span-3">
                    <label class="block font-medium leading-6 text-gray-900">Date Of Birth</label>
                    <div class="mt-2">
                        <input type="date" v-model="student.Dob"
                            class="block w-full rounded-md border-0 py-2 px-3 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm sm:leading-6">
                    </div>
                </div>

                <div class="col-span-full">
                    <label for="street-address" class="block font-medium leading-6 text-gray-900">Address</label>
                    <div class="mt-2">
                        <input type="text" v-model="student.Address"
                            class="block w-full rounded-md border-0 py-2 px-3 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm sm:leading-6">
                    </div>
                </div>
                <div class="col-span-full">
                    <div class="flex items-center justify-end gap-x-6">
                        <button type="button" class="px-3 font-semibold leading-6 text-gray-900">Cancel</button>
                        <button type="submit" @click="save"
                            class="rounded-md bg-indigo-600 px-4 py-2 font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600">Save</button>
                    </div>
                </div>
            </div>
        </div>
        <div class="sm:col-span-4">
            <div class="p-4">
                <label for="table-search" class="sr-only">Search</label>
                <div class="relative mt-1">
                    <div class="absolute inset-y-0 left-0 flex items-center pl-3 pointer-events-none">
                        <svg class="w-5 h-5 text-gray-500 dark:text-gray-400" fill="currentColor" viewBox="0 0 20 20"
                            xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd"
                                d="M8 4a4 4 0 100 8 4 4 0 000-8zM2 8a6 6 0 1110.89 3.476l4.817 4.817a1 1 0 01-1.414 1.414l-4.816-4.816A6 6 0 012 8z"
                                clip-rule="evenodd"></path>
                        </svg>
                    </div>
                    <input type="text" id="table-search"
                        class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-80 pl-10 p-2.5  dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                        placeholder="Search for items">
                </div>
            </div>
            <table class="w-full text-sm text-left text-gray-500 dark:text-gray-400">
                <thead class="text-xs text-gray-700 uppercase bg-gray-50 dark:bg-gray-700 dark:text-gray-400">
                    <tr>
                        <th scope="col" class="px-6 py-3">
                            Name
                        </th>
                        <th scope="col" class="px-6 py-3">
                            Gender
                        </th>
                        <th scope="col" class="px-6 py-3">
                            Phone
                        </th>
                        <th scope="col" class="px-6 py-3">
                            DoB
                        </th>
                        <th scope="col" class="px-6 py-3">
                            Address
                        </th>
                        <th scope="col" class="px-6 py-3">
                        </th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="ret in studentList" :key="ret.Id"
                        class="bg-white border-b dark:bg-gray-800 dark:border-gray-700 hover:bg-gray-50 dark:hover:bg-gray-600">
                        <th scope="row" class="px-6 py-4 font-medium text-gray-900 dark:text-white whitespace-nowrap">
                            {{ ret.Name }}
                        </th>
                        <td class="px-6 py-4">
                            {{ ret.Gender }}
                        </td>
                        <td class="px-6 py-4">
                            {{ ret.Phone }}
                        </td>
                        <td class="px-6 py-4">
                            {{ ret.Dob }}
                        </td>
                        <td class="px-6 py-4">
                            {{ ret.Address }}
                        </td>
                        <td class="px-6 py-4 text-right">
                            <a @click="edit(ret)" href="#" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Edit</a>
                        </td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
</template>
<script>
export default {
    data(){
        return{
            student: {
                Id: '',
                Name: '',
                Gender: '',
                Phone: '',
                Dob: '',
                Address: ''
            },
            studentList: []
        }
    },
    methods:{
        save(){
            if(this.student.Id == ''){
                let id = this.studentList.length + 1;
                this.studentList.push({
                    Id: id,
                    Name: this.student.Name,
                    Gender: this.student.Gender, 
                    Phone: this.student.Phone, 
                    Dob: this.student.Dob, 
                    Address: this.student.Address
                });
                this.student.Id = '';
                this.student.Name = '';
                this.student.Gender = '';
                this.student.Dob = '';
                this.student.Phone = '';
                this.student.Address = '';
            }else{
                this.student = {
                    Id: '',
                    Name: '',
                    Gender: '',
                    Phone: '',
                    Dob: '',
                    Address: ''
                }
            } 
        },
        edit(item){
            this.student = item;
        }
    }
}
</script>