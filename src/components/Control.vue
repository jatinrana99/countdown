<template>
    <button v-on:click="control">{{ title }}</button>
</template>

<script>
export default {
    name:`Control`,
    data(){

    },
    props:[
        'control',
        'time',
        'title'
    ],
}
</script>

<style scoped>

button{
    margin: 8px;
}
</style>