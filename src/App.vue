<template>
    <div id="app">
        <Navigation />
        
        <b-container v-if="!authenticated" id="content-wrap">
            <router-view name="signin" />
        </b-container>

        <b-container v-else id="content-wrap">
            <router-view />
        </b-container>

        <Footer />
    </div>
</template>

<script>
    import Navigation from './components/Navigation'
    import Footer from './components/Footer'
    import 'bootstrap/dist/css/bootstrap.css'
    import 'bootstrap-vue/dist/bootstrap-vue.css'

    export default {
        components: {
            Navigation,
            Footer
        },

        computed: {
            authenticated: true
        },
        getters: {
            authenticated: null
        }
    }
</script>

<style>
    #app {
        position: relative;
        min-height: 100vh;
    }

    #content-wrap {
        padding-bottom: 2.5rem;    /* Footer height */
    }
</style>