<script setup lang="ts">
import Child from '@/components/Child.vue';


function receiveDataFromChild(data: any) {
  console.log("Parent has receiveed data", data);
}
</script>

<template>

  <h1>THIS IS A HOME PAGE</h1>

  <Child name="Child 1" @data="receiveDataFromChild" @no-data="receiveDataFromChild"/>
  
  <Child name="Child 2" @data="receiveDataFromChild" @no-data="receiveDataFromChild"/>

</template>
