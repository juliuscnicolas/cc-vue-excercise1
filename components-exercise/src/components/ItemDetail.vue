<template>
    <div class="item-details inventory-div">
        <div v-if="Object.keys(fruit).length === 0">
            <p>Please Select Fruit</p>
        </div>
        <div v-else>
            <div><b>{{fruit.name}}</b></div>
            <div>{{fruit.description}}</div>
        </div>
       
    </div>
</template>
<script>
export default {
    props: {
        fruit: {}
    }
}
</script>