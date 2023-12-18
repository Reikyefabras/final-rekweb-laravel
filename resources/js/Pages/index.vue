<style scoped>
table{
    border-collapse: collapse;
    width: 80%;
}
th,tr,td{
    border: 1px solid black;
    padding: 5px;
}
th{
    background-color:rgba(209, 212, 212, 0.862);
}
nav{
    margin: 15px;
}
.buttom{
    padding: 5px;
    border: 1px solid;
    text-decoration: none;
    color:white;
    border-radius: 8px;
}
.blue{
    background-color: rgb(52, 115, 230);
}
.green{
    background-color: rgb(9, 183, 32);
}
.red{
    background-color: red;
}
.lebar-aksi{
    width: 200px;
}
td{
    padding: 15px;
}
</style>
<template>
    <div class="container mx-auto pt-5">

        <nav>
            <Link class="buttom blue" href="/post/create">Create post</Link>
        </nav>
    <table class="table">
  <thead>
    <tr>
      <th class="bg-slate-50">Judul Film</th>
      <th>Sutradara</th>
      <th>Sinopsis</th>
      <th class="lebar-aksi">Aksi</th>
    </tr>
  </thead>
  <tbody>
    <tr class="post_block" v-for="post in posts" :key="post.id">
      <td>{{ post.title }}</td>
      <td>{{ post.author }}</td>
      <td>{{ post.content }}</td>
      <td> 
        <Link :href="`/post/edit/${post.id}`" class="buttom green">Edit post</Link> |
        <Link :href="`/post/delete/${post.id}`" method="DELETE" class="buttom red">Delete post</Link>
    </td>
    </tr>
  </tbody>
</table>
    </div>
</template>

<script setup>
import { defineProps } from 'vue';
import {Link } from '@inertiajs/vue3';
defineProps({
    posts: Array
});
</script>