<script setup lang="ts">
    import ListItem from './ListItem.vue';
    type Item = {
        title: string;
        checked?: boolean;
    };
    const GroupsItems: Item[] = [
        { title: 'Leer un libro al mes'},
        { title: 'Hacer ejercicio 3 veces por semana'},
        { title: 'Aprender algo nuevo cada día'},
    ];
</script>

<template>
    <ul >
        <li :key="index" v-for="(item, index) in GroupsItems">
            <ListItem :isChecked="item.checked">
                {{ item.title }}
            </ListItem>
        </li>
    </ul>
</template>

<style scoped>
    ul {
        list-style: none;
        padding: 0;
    };
</style>