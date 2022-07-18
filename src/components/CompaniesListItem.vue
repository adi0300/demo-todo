<script setup>
const props = defineProps({
    name: String,
    city: String,
    employees: Array,
    });
let newName = props.name;
let newLocation = props.city;
let newEmployees = "";
let length = props.employees.length;
for (var i = 0; i < length; i++){
    newEmployees = newEmployees + props.employees[i].name + ", ";

}
</script>

<template>
<table class="table">
    <tr>
    <th>Company name</th>
    <th>Location</th>
    <th>Employees</th>
    </tr>
    <tr>
        <td>{{ newName }}</td>
        <td> {{ newLocation }}</td>
        <td>{{ newEmployees }}</td>
    </tr>
</table>
</template>

<style scoped>
.company{
    font-family: sans-serif;
    font-size: 20px;
}

.table{
    font-family: sans-serif;
    font-size: 16px;
    padding: 10px;
    margin-top: 10px;
}

.table th,td{
    border: 2px solid black;
}
</style>