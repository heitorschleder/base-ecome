<script lang="ts" setup>
</script>
<template>
    <footer class="flex justify-center items-center h-48">
        <div id="logo" class="flex items-center p-3 text-white">
            <img class="max-w-36" src="../footerPages/images/gravata.png" alt="">
            <p class="w-48 p-2">Lorem, ipsum dolor sit amet consectetur adipisicing elit. Repellendus cum dolorum maxime, dolor distinctio.</p>
        </div>
        <main class="w-[50vw] flex justify-evenly text-white">
            <ul class="flex flex-col items-start">
                <h2 class="font-bold text-xl ">About Brand</h2>
                <li><a class="hover:underline " href="">Location</a></li>
                <li><a class="hover:underline " href="">Stores</a></li>
                <li><a class="hover:underline " href="">About Us</a></li>
            </ul>
            <ul class="flex flex-col items-start ">
                <h2 class="font-bold text-xl ">Doubts</h2>
                <li><a class="hover:underline " href="">Delivery</a></li>
                <li><a class="hover:underline " href="">Payment Methods</a></li>
                <li><a class="hover:underline " href="">Guarantee</a></li>
            </ul>
            <ul class="flex flex-col items-start ">
                <h2 class="font-bold text-xl ">Help</h2>
                <li><a class="hover:underline " href="">FAQ</a></li>
                <li><a class="hover:underline " href="">Privacy Policy</a></li>
                <li><a class="hover:underline " href="">Talk To Us</a></li>
            </ul>
        </main>
        <div id="socials" class="flex text-3xl p-5 justify-between">
            <h4 class="mr-4 text-white">Follow us</h4>
            <div class="flex space-x-2">
                <div class="w-10 h-10 p-1 border border-white rounded-full text-3xl hover:bg-[#0866FF] ">
                    <a class="flex text-center" href="https://facebook.com"><i class="ti ti-brand-facebook text-white "></i></a>
                    
                </div>
                <div class="w-10 h-10 p-1 border border-white rounded-full text-3xl hover:bg-[#FE0173]">
                    <a class="flex text-center" href="https://instagram.com"><i class="ti ti-brand-instagram text-white"></i></a>
                    
                </div>
                <div class="w-10 h-10 p-1 border border-white rounded-full text-3xl hover:bg-black">
                    <a class="flex text-center" href="https://x.com"><i class="ti ti-brand-x text-white"></i></a>
                    
                </div>
                <div class="w-10 h-10 p-1 border border-white rounded-full text-3xl hover:bg-red-700">
                    <a class="flex text-center" href="https://youtube.com"><i class="ti ti-brand-youtube text-white"></i></a>
                </div>
            </div>
        </div>
    </footer>
</template>