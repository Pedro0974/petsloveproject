<template>
    <nav :class="{ 'bg-transparent-css': isTop, 'bg-blur': !isTop }" class="container-nav">
        <div class="container-logo">
            <img class="w-20" src="../assets//logo.png" alt="">
            <div>
                <p class="font-bold text-orange-700 text-2xl">Pets</p>
                <p class="font-bold text-blue-700 text-lg -mt-2">Love</p>
            </div>
        </div>

        <div class="container-links">
            <router-link class="links" to="/#home">Home</router-link>
            <router-link class="links" to="/#about">About</router-link>
            <router-link class="links" to="/#services">Services</router-link>
            <router-link class="links" to="/#contacts">Contacts</router-link>
        </div>
    </nav>
</template>

<script>
export default {
    name: 'NavBar',

    data() {
        return {
            isTop: true,
        };
    },
    mounted() {
        window.addEventListener('scroll', this.handleScroll);
    },
    destroyed() {
        window.removeEventListener('scroll', this.handleScroll);
    },
    methods: {
        handleScroll() {
            this.isTop = window.scrollY === 0;
        },
    },

}
</script>

<style scoped lang="scss">
.container-nav {
    @apply flex flex-col md:flex-row md:justify-between items-center px-24 md:py-0 fixed z-10 w-full transition-all duration-300 ease-in-out;
}

.bg-transparent-css {
    @apply bg-transparent;
}

.bg-blur {
    @apply backdrop-filter backdrop-blur-md;
    background-color: rgba(0, 0, 0, 0.2); 
}

.container-logo {
    @apply flex items-center;
}

.container-links {
    @apply flex gap-6;
}

.links {
    @apply text-blue-700 hover:text-blue-500 text-xl font-bold;
}
</style>