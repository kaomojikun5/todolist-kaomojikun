<script setup lang="ts">
import { ref } from 'vue'

interface Item {
    name: string
    price: number
}

const iems = ref<Item[]>([
    { name: 'たまご', price: 100 },
    { name: 'りんご', price:160 }

])

</script>
<template>
    <div>
        <div>Itemlist</div>
        <ul>
            <li v-for="item in items" :key="item.name">
                <div>名前: {{ item.name }}</div>
                <div>{{ item.price }}</div>
            </li>
        </ul>
        <div>
            <label>
                名前
                <input v-model="newItemName" type="text" />
            </label>
            <label>
                価格
                <input v-model="newItemPrice" type="number" />
            </label>
            <button @click="addItem">追加</button>
        </div>
    </div>
</template>

<style></style>