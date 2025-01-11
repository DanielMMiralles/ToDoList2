<script setup lang="ts">
    import { ref } from 'vue';
    import type { Ref } from 'vue';
    import ListItem from './ListItem.vue';
    
    type Item = {
        title: string;
        checked?: boolean;
    };
    const GroupsItems: Ref<Item[]> = ref([
        { title: 'Leer un libro al mes'},
        { title: 'Hacer ejercicio 3 veces por semana'},
        { title: 'Aprender algo nuevo cada día'},
    ]);

    const updateItem = (item:Item): void => {
        const updatedItem = findItemList(item);
        if(updatedItem){
            toggleItemCheck(updatedItem);
        };
    };

    const findItemList = (item : Item): Item | undefined => {
        return GroupsItems.value.find((groupItem) => groupItem.title === item.title);
    };

    const toggleItemCheck = (item: Item): void => {
        item.checked = !item.checked;
    };
</script>

<template>
    <ul >
        <li :key="index" v-for="(item, index) in GroupsItems">
            <ListItem :isChecked="item.checked" @updateItem="() => updateItem(item)">
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