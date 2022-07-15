<script setup>
defineProps({
    id: Number,
    title: String,
    completed: Boolean
})
</script>

<template>

     <input class="grid-item-checkbox" type="checkbox" :checked="completed" />
      <p class="grid-item">{{ title }}</p>
     <button class="grid-item-button">DELETE</button>

</template>

<style scoped>

.grid-item{
    border-style: solid;
    border-color: black;
    border-width: 1px;
    border-radius: 6px;
    padding: 6px;
    font-family: sans-serif;
    text-align: center;
    font-size: 20px;
    grid-column: 2;
    justify-self: center;
}
.grid-item-button{
    background-color: white;
    border-style: solid;
    border-color: transparent;
    border-radius: 6px;
    border-width: 1px;
    height: 55px;
    width: 70px;
    margin-right: 20px;
    grid-column: 3;
    justify-self: right;
    font-family: sans-serif;

}

.grid-item-button:hover{
    background-color: orange;
    color: white;
    opacity: 70%;
    cursor: pointer;
    border: 1px solid red;
}

.grid-item-checkbox{
    border-style: solid;
    border-color: black;
    border-width: 1px;
    grid-column: 1;
    width: 5%;
    justify-self: center;
}
</style>
