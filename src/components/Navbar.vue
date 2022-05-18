<template>
    <div id="navbar" class="h-20 w-full bg-green-500 text-white flex justify-between items-center px-12 font-poppins">
        <div class="flex gap-4 items-center">
            <img src="../assets/img/kelamas.png" alt="" class="h-10">
            <p class="font-bold text-xl">HMP Kelamas</p> 
        </div>
        <ul class="text-lg font-medium flex gap-8 items-center">
            <li><router-link to="/" class="flex gap-2"><i class="bi bi-house"></i>Home</router-link></li>
            <li><router-link to="/about" class="flex gap-2"><i class="bi bi-people"></i>Tentang Kami</router-link></li>
            <li><router-link to="/about" class="flex gap-2"><i class="bi bi-diagram-2"></i>Struktur Bidang 1</router-link></li>
            <li><router-link to="/about" class="flex gap-2"><i class="bi bi-menu-up"></i>Program Kerja</router-link></li>
            <li class="flex gap-4 items-center"><input type="text" class="border-2 border-white bg-transparent outline-none rounded-md px-4 py-1" v-if="search"><i class="bi bi-search cursor-pointer" @click="search = !search"></i></li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'Navbar',
    components: {},
    data() {
        return {
            search: false
        }
    }
}
</script>