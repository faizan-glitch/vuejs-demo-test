<script setup lang="ts">
import { defineProps, defineEmits, ref } from 'vue';
import { useCounterStore } from '@/stores/counter';

const store = useCounterStore();

defineProps({
    name: {
        type: String,
        required: true
    },
});

// let counter = ref(0);

const emitter = defineEmits(["data", "no-data"]);

function sendDataToParent() {
    console.log("Sending data to parent...");
    emitter('data', "Hello parent");
    emitter('no-data', "You get not data");
}

// function increment() {
//     counter.value = counter.value + 1;
// }

</script>

<template>
    <div>
        <h1>Child Component {{name}}</h1>

        <button @click="sendDataToParent"> Send Data To Parent</button>

        <h1> {{ store.count }}</h1>

        <button @click="store.increment">Increment</button>
    </div>

</template>