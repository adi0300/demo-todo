<script setup>
import PageContainer from '../components/PageContainer.vue';
import TodoList from '../components/TodoList.vue';
</script>

<template>
<suspense>
    <TodoList />
</suspense>
</template>