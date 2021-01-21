<template>
     <div class="items-container inventory-div row no-margin">
            <div class="col-sm-12">Item List In Here</div>
           
             <div 
                v-for="(fruit, index) in fruits" 
                :key="fruit.name" 
                :class="setItemListClass(fruit.stock > 0)"
                @click="getItemDetails(fruit)">

                <div :key="index" class="col-sm-6">Name: </div>
                <div class="col-sm-6">{{fruit.name}}</div>
                <div class="col-sm-6">Price: </div>
                <div class="col-sm-6">{{fruit.price}}</div>
                <div class="col-sm-6">Stock: </div>
                <div class="col-sm-6">{{setStockValue(fruit.stock)}}</div>
            </div>

        </div>
</template>
<script>
import { eventBus } from '../main';
export default {
    props: {
        fruits: {}
    },
    methods: {
        setItemListClass(hasStock){
            const itemListClassValue = hasStock ? '' : 'out-of-stock';
            return `col-sm-4 item row no-margin no-padding ${itemListClassValue}`;
        },
        getItemDetails(fruit){
            eventBus.$emit('fruit', fruit)
        },
        setStockValue(value) {
            return value === 0 ? 'Out of Stock' :  value;
        }
    }
}
</script>
