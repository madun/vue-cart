<template>
    <div>
        <ul class="list-group mt-4">
            <li class="list-group-item" v-for="item in items" :key="item.id">
                {{ item.title }} - ${{ item.price }}
                <button class="btn badge badge-danger float-right"
                @click="$emit('remove-from-cart', item)">Remove</button>
            </li>
        </ul>
        <div v-if="items.length !== 0 ">
            <div class="card p-3 my-5">
                <h4 class="text-center">${{ total }}</h4>
            </div>
            <button class="btn btn-info form-control"
                @click="$emit('pay')"
            >Pay Now</button>
        </div>
    </div>
</template>
<script>
export default {
    props: ['items'],
    computed: {
     total(){
         return this.items.reduce((acc, item) => acc + Number(item.price), 0)
     }   
    }
}
</script>

