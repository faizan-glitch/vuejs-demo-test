<script setup lang="ts">
  import { ref } from 'vue';
  let name = ref("Faizan");

  let age = ref(10);

  let fruits = ref(["apple", "banana", "mango", "kiwi", "strawberry"]);


  let todos = [
    {
      id: 1,
      title: "Buy Groceries",
      done: false
    },
    {
      id: 2,
      title: "Clean House",
      done: false
    },
    {
      id: 3,
      title: "Walk the dog",
      done: false
    }
  ]

  function clicked() {
    // alert("I was clicked");

    fruits.value.pop();

    console.log(fruits);
  }

  function checkItem (id: number) {
    console.log(id);
  }
</script>

<template>
  <div>
    <!-- <h1>Hello World</h1>
    <p>{{name}}</p>
    
    <p v-if="age >= 50"> You are Senior citizen </p>
    <p v-else-if="age >= 19"> You are an adult</p>
    <p v-else> You are a child </p>


    <ol>
      <li v-for="(fruit, index) in fruits"> {{index}}. {{ fruit }}</li>
    </ol>

    <button @click="clicked">Click Me</button>

    <br/>
    <br/>

    <ol>
      <li v-for="todo in todos" @click="checkItem(todo.id)">{{todo.title}}</li>
    </ol> -->

    <nav>
      <router-link to="/">Home</router-link>
      <router-link to="/contact">Contact</router-link>
      <router-link to="/about">About</router-link>
    </nav>

    <router-view></router-view>

    <footer>This is my footer</footer>

  </div>
</template>

<style scoped>
  h1 {
    background-color: pink;
  }
</style>
