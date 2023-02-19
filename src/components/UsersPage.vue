<template>
  <div class="container">
    <table class="table">
      <thead>
      <tr>
        <th scope="col">Id</th>
        <th scope="col">Name</th>
        <th scope="col">Email</th>
        <th scope="col">Website</th>
        <th scope="col">Compony</th>
      </tr>
      </thead>
      <tbody>
      <tr v-for="user in users" :key="user.id">
        <th scope="row">{{user.id}}</th>
        <td>{{user.name}}</td>
        <td>{{user.email}}</td>
        <td>{{user.website}}</td>
        <td>{{user.company.name}}</td>
      </tr>


      </tbody>
    </table>
  </div>

</template>
<script setup>

import {onMounted, ref} from "vue";
import axios from "axios";

const users = ref(null);
onMounted(()=>{
  axios.get("https://jsonplaceholder.typicode.com/users").then( (response) => {
users.value = response.data;
        console.log(users.value)
      }
  );

})

</script>
