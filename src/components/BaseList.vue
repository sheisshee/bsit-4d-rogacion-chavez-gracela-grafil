<script setup>
let numbers = [0,1,2,3,4]
</script>

<template>
    <ul>
        <li v-for="number in numbers">
            {{ number }} </li>
        
    </ul>
</template>