<script setup lang="ts">
import { onBeforeMount, onMounted, onBeforeUnmount, onUnmounted, ref, nextTick } from 'vue';

  let loading = ref(true);

  const mybtn = ref();

  onMounted(() => {
    console.log("I am mounted");
    console.log(mybtn.value);
    mybtn.value.value = "Somehingojasdapsd()";
  })

  onBeforeMount(async () => {
    console.log("Before Mounted");

    try {
      await fetch("https://google.com");
      
    } catch (error) {
    }
    finally {
      loading.value = false;
    }
  });


  onBeforeUnmount(() => {
    console.log("I am about to leave");
    alert("Do you want to leave?")
  })

  onUnmounted(() => {
    console.log("I have left");
  })

</script>

<template>
  <div class="about">
    <h1>This is an about page</h1>

    <h2 v-if="loading">Loading...</h2>

    <input type="text" name="" id="" ref="mybtn">
  </div>
</template>

<style>

</style>
