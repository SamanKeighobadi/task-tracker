<template>
  <header>
    <h1>{{title}}</h1>
    <Button />
  </header>
</template>


<script>
import Button from './Button.vue';
export default {
    name: "Header",
    props:{
        title:String
    },
    components: { Button }
};
</script>

<style>
    header{
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin: 0 0 20px 0;
    }
</style>