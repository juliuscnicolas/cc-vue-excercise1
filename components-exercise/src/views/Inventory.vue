<template>
    <div>
        <item-list
            :fruits="items"
        ></item-list>

        <item-detail
            :fruit="fruit"
        ></item-detail>
        
    </div>
</template>

<script>
import ItemList from '../components/ItemList'
import ItemDetail from '../components/ItemDetail'
import { eventBus } from '../main';
export default {
    components: {
        ItemList,
        ItemDetail
    },
    data() {
        return {
            items: [
                {
                    name: 'Apple',
                    price: 4.99,
                    stock: 5,
                    description: 'a succulent large apple'
                },
                {
                    name: 'Mango',
                    price: 6.99,
                    stock: 3,
                    description: 'a ripe queen mango'
                },
                {
                    name: 'Lemon',
                    price: 3.99,
                    stock: 0,
                    description: 'very sour fruit'
                }
            ],
            fruit: {}
        }
    },
    created() {
        eventBus.$on('fruit', fruit => {
            this.fruit = fruit;
        })
    }
}
</script>

<style>
.inventory-div {
    width: 100%;
    padding: 10px;
    border: 2px solid black;
    border-radius: 5px;
    margin-bottom: 10px !important;
}

.items-container .item {
    padding: 5px !important;
    border: 1px solid black;
    border-radius: 2px;
    cursor: pointer;
    background-color: lightgreen;
}

.items-container .item.out-of-stock {
    background-color: lightcoral;
}
</style>