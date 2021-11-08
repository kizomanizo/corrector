<template>
    <div>
        <b-navbar type="dark" variant="dark">
            <b-container>
                <b-navbar-nav>
                    <b-navbar-brand>Totalizer App</b-navbar-brand>
                    <b-nav-item href="#" v-if="$route.name!='home'" @click.prevent="getHome">Home</b-nav-item>
                    <b-nav-item href="#" v-if="$route.name!='data'" @click.prevent="getData">Data</b-nav-item>
                </b-navbar-nav>
                <b-navbar-nav ml="auto">
                    <b-nav-text><strong>></strong></b-nav-text>
                    <b-nav-item href="#" v-if="$route.name!='login'" @click.prevent="signOut">Logout</b-nav-item>
                </b-navbar-nav>
            </b-container>
        </b-navbar>
    </div>
</template>

<script>
export default {
    name: 'HelloWorld',
    props: {
        msg: String
    },
    methods: {
        signOut() {
            this.$store.dispatch('auth/signOut');
            this.$router.push('/login');
        },
        getHome() {
            this.$store.dispatch('auth/getHome');
            this.$router.push('/home');
        },
        getData() {
            this.$store.dispatch('auth/getData');
            this.$router.push('/data');
        },
    }
}
</script>


