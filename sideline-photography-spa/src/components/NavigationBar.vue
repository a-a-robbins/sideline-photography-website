<template>
    <nav :class="navbarClasses">
        <div class="container-fluid">
            <a class="navbar-brand" href="#">
                <img src="../assets/sp-logo.png" alt="sideline photo logo" width="30" height="24">
            </a>
            <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                <li v-for="(page, index) in pages" class="nav-item" :key="index">
                    <navbar-link
                        :page="page"
                        :isActive="activePage === index"
                        @click.prevent="navLinkClick(index)"
                    ></navbar-link>
                </li>
            </ul>
            <form class="d-flex">
                <button class="btn btn-danger" @click.prevent="changeTheme">Toggle Navbar</button>
            </form>
        </div>
    </nav>
</template>

<script>
import NavbarLink from './NavbarLink.vue';

export default {
    components: {NavbarLink},
    props: ['pages', 'activePage', 'navLinkClick'],
    data() {
        return {
            theme: 'dark'
        };
    }
    ,
    computed: {
        navbarClasses() {
            return [`navbar-${this.theme}`, `bg-${this.theme}`, 'navbar', 'navbar-expand-lg'];
        }
    },
    methods: {
        changeTheme() {
            this.theme = this.theme === 'light' ? 'dark' : 'light';
        }
    }
}
</script>