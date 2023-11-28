<template>
    <nav :class="{ 'bg-transparent-css': isTop, 'bg-blur': !isTop }" class="container-nav">
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
    @apply flex flex-col md:flex-row md:justify-between items-center px-24 py-6 md:py-0 fixed z-10 w-full transition-all duration-300 ease-in-out;
}

.bg-transparent-css {
    @apply bg-transparent;
}

.bg-blur {
    @apply backdrop-filter backdrop-blur-md;
    background-color: rgba(0, 0, 0, 0.5); 
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