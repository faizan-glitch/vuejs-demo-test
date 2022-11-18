<script setup lang="ts">
import { watch, ref } from 'vue';
import Child from '@/components/Child.vue';

let obj = ref({
  name: "Faizan",
  age: 24
});

function receiver(data: any) {
  console.log("data is in contact", data);
}

watch(obj, (newValue, oldValue) => {
  console.log("obj has changed. Trigger side effect");
});

const changeObj = () => {
  obj.value = {
    ...obj.value,
    name: "SOmething"
  }
}

</script>

<template>
  <div>
    <h1>This is an contact page</h1>
    <Child name="John Doe" @data="receiver"/>

    <button @click="changeObj">Change name</button>
  </div>
</template>

<style>

</style>
