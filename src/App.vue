<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div class="container mx-auto">
    <header>
    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <nav class="grid grid-cols-10">
        <RouterLink class="p-3 bg-slate-400 hover:bg-indigo-400" to="/">Home</RouterLink>
        <RouterLink class="p-3 bg-slate-400 hover:bg-indigo-400" to="/testObjectList">Test Object List</RouterLink>
        <RouterLink class="p-3 bg-slate-400 hover:bg-indigo-400" to="/blog">Blog</RouterLink>
        <RouterLink class="p-3 bg-slate-400 hover:bg-indigo-400" to="/personal">Personal Info</RouterLink>
        <RouterLink class="p-3 bg-slate-400 hover:bg-indigo-400" to="/students">Students</RouterLink>
      </nav>
    </div>
  </header>

  <div class="m-2 p-4 border border-gray-300 rounded-md ">
    <RouterView />
  </div>
  </div>
</template>
