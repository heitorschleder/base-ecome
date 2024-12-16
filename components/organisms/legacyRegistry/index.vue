<script setup lang="ts">
import buttonEdit from '~/components/ui/buttonEdit/buttonEdit.vue';
import FooterPages from '~/components/organisms/footerPages/index.vue';

import { ref } from 'vue';

const filters = ref({
    product: '',
    amount: null,
    quantity: null,
    status: ''
});

const applyFilters = () => {
    console.log('filtro foi:', filters.value);
};

function testefun() {
    console.log('Button clicked!');
}
const products = ref([
    {
        image: 'https://png.pngtree.com/png-clipart/20190614/original/pngtree-tie-glyph-black-icon-png-image_3755399.jpg',
        product: 'Heitor de Oliveira Schleder',
        model: 'v 1.0',
        amount: 'R$ 230,00',
        quantity: 200,
        status: 'active'
    },
    {
        image: 'https://png.pngtree.com/png-clipart/20190614/original/pngtree-tie-glyph-black-icon-png-image_3755399.jpg',
        product: 'DTR 001',
        model: 'v 1.1',
        amount: 'R$ 150,00',
        quantity: 150,
        status: 'active'
    },
    {
        image: 'https://png.pngtree.com/png-clipart/20190614/original/pngtree-tie-glyph-black-icon-png-image_3755399.jpg',
        product: 'Luizinha gameplays',
        model: 'v 2.0',
        amount: 'R$ 300,00',
        quantity: 100,
        status: 'out'
    },
    {
        image: 'https://png.pngtree.com/png-clipart/20190614/original/pngtree-tie-glyph-black-icon-png-image_3755399.jpg',
        product: 'Lorem Ipsolorem',
        model: 'v 3.0',
        amount: 'R$ 450,00',
        quantity: 50,
        status: 'draft'
    },
    {
        image: 'https://png.pngtree.com/png-clipart/20190614/original/pngtree-tie-glyph-black-icon-png-image_3755399.jpg',
        product: 'Luizinha gameplays',
        model: 'v 2.0',
        amount: 'R$ 300,00',
        quantity: 100,
        status: 'out'
    },

    {
        image: 'https://png.pngtree.com/png-clipart/20190614/original/pngtree-tie-glyph-black-icon-png-image_3755399.jpg',
        product: 'Luizinha gameplays',
        model: 'v 2.0',
        amount: 'R$ 300,00',
        quantity: 100,
        status: 'out'
    },

    {
        image: 'https://png.pngtree.com/png-clipart/20190614/original/pngtree-tie-glyph-black-icon-png-image_3755399.jpg',
        product: 'Luizinha gameplays',
        model: 'v 2.0',
        amount: 'R$ 300,00',
        quantity: 100,
        status: 'out'
    },
    {
        image: 'https://png.pngtree.com/png-clipart/20190614/original/pngtree-tie-glyph-black-icon-png-image_3755399.jpg',
        product: 'Luizinha gameplays',
        model: 'v 2.0',
        amount: 'R$ 300,00',
        quantity: 100,
        status: 'out'
    },
    {
        image: 'https://png.pngtree.com/png-clipart/20190614/original/pngtree-tie-glyph-black-icon-png-image_3755399.jpg',
        product: 'Luizinha gameplays',
        model: 'v 2.0',
        amount: 'R$ 300,00',
        quantity: 100,
        status: 'out'
    },
]);
</script>
<template>
    <div class="bg-[#0f0f2f] text-white h-screen w-screen flex flex-col">
        <header class="text-center p-4">
            <h1 class="text-3xl">Products Registration</h1>
        </header>
        <div class="flex flex-1">
            <nav class="flex-col max-w-[20vw] p-10 text-center space-y-6">
                <img class="w-24 h-24 border border-white rounded-full" src="~/assets/images/gravata.png" alt="">
                <ul class="text-left space-y-3">
                    <li><a class="hover:underline" href="">My Products</a></li>
                    <li><a class="hover:underline" href="">Create Product</a></li>
                </ul>
            </nav>
            <main class="flex-1 max-w-[70vw] border border-white">
                <Table class="border border-white h-16">
                    <TableHeader>
                        <TableRow>
                            <TableHead class="w-[100px]">Image</TableHead>
                            <TableHead>Product</TableHead>
                            <TableHead>Model</TableHead>
                            <TableHead>Amount</TableHead>
                            <TableHead>Quantity</TableHead>
                            <TableHead>Action</TableHead>
                            <TableHead class="text-right">Status</TableHead>
                        </TableRow>
                    </TableHeader>

                    <TableBody>
                        <TableRow v-for="(item, index) in products" :key="index">
                            <TableCell class="font-medium"><img class="w-11 h-11 border border-white" :src="item.image"
                                    alt=""></TableCell>
                            <TableCell>{{ item.product }}</TableCell>
                            <TableCell>{{ item.model }}</TableCell>
                            <TableCell>{{ item.amount }}</TableCell>
                            <TableCell>{{ item.quantity }}</TableCell>
                            <TableCell>
                                <buttonEdit @click="testefun()" />
                            </TableCell>
                            <TableCell class="text-right">{{ item.status }}</TableCell>
                        </TableRow>
                    </TableBody>
                </Table>
            </main>
            <aside class="flex-none max-w-[30vw] p-4 border border-gray-300 rounded">
                <div class="flex text-left p-2 mb-4">
                    <i class="text-3xl ti ti-filter mr-3"></i>
                    <h2 class="text-3xl">Filters</h2>
                </div>

                <div class="mb-4">
                    <label for="product" class="block text-xl">Product:</label>
                    <input id="product" type="text" v-model="filters.product"
                        class="mt-1 block w-full border text-black border-gray-300 rounded-md shadow-sm p-2"
                        placeholder="product name" />
                </div>

                <div class="mb-4">
                    <label for="amount" class="block text-xl">Amount:</label>
                    <input id="amount" type="number" v-model="filters.amount"
                        class="mt-1 block w-full border text-black border-gray-300 rounded-md shadow-sm p-2"
                        placeholder="price" />
                </div>

                <div class="mb-4">
                    <label for="quantity" class="block text-xl">Quantity:</label>
                    <input id="quantity" type="number" v-model="filters.quantity"
                        class="mt-1 block w-full border text-black border-gray-300 rounded-md shadow-sm p-2"
                        placeholder="quantity" />
                </div>

                <div class="mb-4">
                    <label for="status" class="block text-xl">Status:</label>
                    <select id="status" v-model="filters.status"
                        class="mt-1 block w-full border text-black border-gray-300 rounded-md shadow-sm p-2 text-black">
                        <option value="available">availabe</option>
                        <option value="out_of_stock">out</option>
                        <option value="discontinued">discontinued</option>
                        <option value="discontinued">draft</option>
                    </select>
                </div>

                <button @click="applyFilters" class="w-full bg-blue-500 text-white rounded-md py-2">
                    Apply Filters
                </button>
            </aside>
        </div>
        <FooterPages />
    </div>
</template>