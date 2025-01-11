<script setup lang="ts">
</script>

<template>
    <header>
        <h1><span class="icon" aria-hidden="true">ToDo List</span></h1>
        <p>Goals 2025</p>
    </header>
</template>

<style scoped>
    header {
        border-bottom: #333 1px solid;
        background-color: #fff;
    }
    header::after {
        content: '';
        display: block;
        height: 1px;
        box-shadow: 0px 0px 10px 0px rgb(0, 0, 0, 0.65);
    }
    h1 {
        font-size: 2rem;
    }

    h1 .icon{
        font-size: 1rem;
        vertical-align: middle;
    }
</style>