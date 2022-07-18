<script setup>
import { findDir } from '@vue/compiler-core';
import axios from 'axios';
import {ref, reactive} from 'vue';
import CompaniesListItem from './CompaniesListItem.vue';

let companies = ref();
const firstCompany = ref("");

function handleShowCompanies(){
    axios.get('http://localhost:8081/getCompanies')
         .then((response) => {
            companies.value = response.data.data.companies;  
            console.log(companies.value);   
            console.log(companies.value[1].employees);
           // firstCompany.value = companies[0].name + " " + companies[0].location.city + " " + companies[0].employees[0].name + " ";  
         });
}

</script>

<template>
<button class="button" @click="handleShowCompanies">Show all companies</button>

<div>
    <CompaniesListItem 
v-for="company of companies"
:key = "company.name"
:name ="company.name"
:city="company.location.city"
:employees="company.employees"
/>
</div>

</template>

<style scoped>
.button{
    background-color: orange;
    color: white;
    border-style: solid;
    border-color: transparent;
    border-radius: 6px;
    border-width: 1px; 
    margin-left: 8px;
    margin-bottom: 8px;
    margin-top: 24px;
    padding: 22px;
    width: 15%;
    font-family: sans-serif;
    font-size: 12px;
}

.button:hover{
    background-color: white;
    color: black;
    opacity: 70%;
    cursor: pointer;
    border: 1px solid red;
}
</style>