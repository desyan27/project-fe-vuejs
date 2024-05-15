<template>
    <div class="w-full max-w-sm bg-white border border-gray-200 rounded-lg shadow">
        <a href="#">
            <img class="p-8 rounded-t-lg" :src="product.photo" alt="product image" />
        </a>
        <div class="px-5 pb-5">
            <a href="#">
                <h5 class="text-xl font-semibold tracking-tight text-gray-900">{{ product.name }}</h5>
            </a>
            <div class="flex items-center justify-between">
                <span class="text-3xl font-bold text-gray-900">Rp. {{ product.price }}</span>
                <a href="#"
                    class="text-white bg-zinc-950 hover:bg-zinc-600 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center">Beli</a>
            </div>
        </div>
    </div>

</template>
<script>
export default {
    name: 'Product',
    props: ['product']
};
</script>