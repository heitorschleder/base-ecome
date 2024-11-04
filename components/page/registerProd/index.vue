<script setup lang="ts">
import FooterPages from '~/components/elements/FooterPages';

</script>
<template>
    <body class="bg-[#0f0f2f] text-white h-screen w-screen flex flex-col">
        <header class=" p-4">
            <h1>Cadastro de Produtoss</h1>
        </header>
        <div class="flex flex-1">
            <nav class="flex-none max-w-[20vw] p-10 text-center ">
                <ul class="text-left">
                    <li>Meus Produtos</li>
                    <li>Criar Produto</li>
                </ul>
            </nav>
            <main class="flex-1 max-w-[60vw] p-4">
                <Table>
                    <TableCaption>A list of your recent invoices.</TableCaption>
                    <TableHeader>
                        <TableRow>
                            <TableHead class="w-[100px]">
                                Invoice
                            </TableHead>
                            <TableHead>Status</TableHead>
                            <TableHead>Method</TableHead>
                            <TableHead class="text-right">
                                Amount
                            </TableHead>
                        </TableRow>
                    </TableHeader>
                    <TableBody>
                        <TableRow>
                            <TableCell class="font-medium">
                                INV001
                            </TableCell>
                            <TableCell>Paid</TableCell>
                            <TableCell>Credit Card</TableCell>
                            <TableCell class="text-right">
                                $250.00
                            </TableCell>
                        </TableRow>
                    </TableBody>
                </Table>
            </main>
            <aside class="flex-none max-w-[30vw]  p-4">
                <div class="flex text-left p-2 ">
                    <i class="text-xl ti ti-filter mr-3"></i>
                    <h2>Filtros</h2>
                </div>
                
            </aside>
        </div>
        <FooterPages />
    </body>
</template>