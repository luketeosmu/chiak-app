<template>
    <div class="border-2 bg-white">
        <div @click="select(item.id)" class="px-6 flex items-center justify-between mx-auto itemlist" text="Select Item"
        :class="[item.id == selected.id ? 'select' : '', 'item']">
            <div>
                <h1 class="text-lg mb-3"> {{ item.name }} </h1>
                <div class="flex justify-between items-center">
                    <h1 class="text-md mr-5"><b>${{ item.price.toFixed(2) }}</b></h1>
                    <h1 v-if="this.index == 0" class="text-green-600 text-sm">Best Match!</h1>
                </div>
            </div>
            <img class="ml-3 py-2" :src=item.imgUrl width="120" height="120">
        </div>
    </div>
</template>

<script>
export default {
    name: 'CatalogItem',
    props: {
        item: Object,
        index: Number,
        selected: Object
    },
    methods: {
        select(id) {
           this.$emit('select-item', id)
        }
    },
}
</script>

<style>
.itemlist{
    cursor: pointer;
}
.item.select{
    border-left: 5px solid;
    border-color: rgb(21 128 61);
}
</style>