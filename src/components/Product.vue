<template>
    <div class="card mt-4">
        <img class="card-img-top" :src="product.image">
        <div class="card-body">
            <h5 class="text-center card-title">{{ product.title }}</h5>
            <p class="text-center text-muted card-text display-4">$ {{ Number(product.price).toFixed() }}</p>
        </div>
        <div class="card-footer text-center">
            <button class="btn btn-success"
                :disabled="isInCart"
                @click="$emit('add-to-cart', product)">
            {{ isInCart ? 'Added To Cart' : 'Add To Cart' }}
            </button>
        </div>
    </div>
</template>

<script>
export default {
    props: ['product', 'isInCart']
}
</script>

