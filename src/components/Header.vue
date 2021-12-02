<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-dark fixed-top" :class="{'navbar-shrink': !showNavbar }" id="mainNav">
        <div class="container h-100">
            <div class="d-flex hamburger-menu f-center">
                <router-link class="navbar-brand js-scroll-trigger" to="/"> <img src="logo/cinemakuy.png" alt="CinemaKuy Logo"></router-link>
                <div class="ml-auto">
                    <b-button v-b-toggle.navbarResponsive class="navbar-toggler btn-secondary navbar-toggler-right" type="button">
                        <i class="fas fa-bars"></i>
                    </b-button>
                </div>  
            </div>
            <b-collapse id="navbarResponsive" class="collapse navbar-collapse justify-content-lg-start">
                <ul class="navbar-nav">
                    <li class="nav-item d-flex">
                        <form class="searchbar w-100" @submit.prevent="onSearch">
                            <input class="search_input" type="text" name="" placeholder="Cari Sesuatu...">
                            <div class="search_icon"><i class="fas fa-search"></i></div>
                        </form>
                    </li>
                </ul>
                <ul class="navbar-nav ml-auto text-center">
                    <li class="nav-item">
                        <div>
                            <img src="logo/imax-logo.png" alt="IMAX Logo" class="mx-1">
                            <img src="logo/dolby-logo.png" alt="Dolby Logo" class="mx-1">
                        </div>
                    </li>
                </ul>
                <ul class="navbar-nav mt-2 text-center menus-sidebar-dropdown">
                    <li class="nav-item"><router-link to="/" class="text-white">Now PLaying</router-link></li>
                    <li class="nav-item"><router-link to="/" class="text-white">Coming Soon</router-link></li>
                    <li class="nav-item"><router-link to="/" class="text-white">Theatre</router-link></li>
                    <li class="nav-item"><router-link to="/" class="text-white">Promotion</router-link></li>
                    <li class="nav-item"><router-link to="/" class="text-white">Informations</router-link></li>
                </ul>
            </b-collapse>
        </div>
    </nav>
  </div>
</template>

<script>
export default {
    data () {
        return {
            showNavbar: true,
            lastScrollPosition: 0,
        }
    },
    mounted () {

    },
    beforeDestroy () {
        window.removeEventListener('scroll', this.onScroll)
    },
    methods: {
        onScroll () {
            const currentScrollPosition = window.pageYOffset || document.documentElement.scrollTop
            if (currentScrollPosition < 30) {
                this.showNavbar = true
            } else {
                this.showNavbar = false
            }
        },
    }
}
</script>

<style scoped>

</style>