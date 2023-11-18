<template>
 
    <nav class="container-nav">
        <div class="container-logo">
            <img class="w-24" src="../assets//logo.png" alt="">
            <div>
                <p class="font-bold text-orange-700 text-3xl">Pets</p>
                <p class="font-bold text-blue-700 text-xl -mt-2">Love</p>
            </div>
        </div>

        <div class="container-links">
            <router-link class="links" to="/">Home</router-link>
            <router-link class="links" to="/">About</router-link>
            <router-link class="links" to="/">Services</router-link>
            <router-link class="links" to="/">Contacts</router-link>
        </div>
    </nav>
 
</template>

<script>
export default {
  name: 'NavBar',
}
</script>

<style scoped lang="scss">

.container-nav {
    @apply flex justify-between items-center bg-green-500 px-24 fixed z-10 w-full
}

.container-logo {
    @apply flex items-center
}

.container-links {
    @apply flex gap-6
}

.links {
    @apply text-blue-900 hover:text-blue-700 text-xl font-bold
}

</style>
