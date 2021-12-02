<template>
    <div>
        <b-button v-b-toggle.sidebar-1 id="sidebar-privacy" class="d-none"><i class="fas fa-bars menu-size"></i></b-button>
        <b-sidebar id="sidebar-1" class="d-none d-lg-block" shadow visible>
        <div class="text-left sidebar-list">
            <div class="sidebar-top">
                <div class="sidebar-item item-active"><router-link to="/" class="btn sidebar-item">Now PLaying</router-link></div>
                <div class="sidebar-item"><router-link to="/" class="btn sidebar-item">Coming Soon</router-link></div>
                <div class="sidebar-item"><router-link to="/" class="btn sidebar-item">Theatre</router-link></div>
                <div class="sidebar-item"><router-link to="/" class="btn sidebar-item">Promotion</router-link></div>
                <div class="sidebar-item"><router-link to="/" class="btn sidebar-item">Informations</router-link></div>
            </div>
        </div>
        </b-sidebar>
    </div>
</template>

<script>
export default {

}
</script>

<style>

</style>