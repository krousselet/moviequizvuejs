<template>
    <nav class="navbar navbar-expand-lg bg-body-tertiary">
        <div class="container-fluid">
            <!-- <a class="navbar-brand" href="#">MovieQuiz</a> -->
            <img src="./assets/images/Navbar/MOVIEQUIZDarkModDesktop.svg" alt="image d'un logo" id="logo">
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent"
                aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                    <li class="nav-item" v-for="(page, pageIndex) in pages " :key="pageIndex">
                        <a class="nav-link" @click.prevent="activePage = pageIndex" aria-current="page" href="#"
                            :class="{ active: activePage === pageIndex }"
                            :title="`${page.link.title}${page.link.content}`">{{
                                page.link.content }}</a>
                    </li>
                    <li class="nav-item dropdown">
                        <a class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown"
                            aria-expanded="false">
                            Dropdown
                        </a>
                        <ul class="dropdown-menu">
                            <li v-for="(dropdown, dropdownIndex) in dropdowns" :key="dropdownIndex"><a class="dropdown-item"
                                    href="#">{{ dropdown.link.content }}</a></li>
                            <li>
                                <hr class="dropdown-divider">
                            </li>
                            <li><a class="dropdown-item" href="#">Something else here</a></li>
                        </ul>
                    </li>
                </ul>
            </div>
        </div>
    </nav>
</template>
<script>
export default {
    props: ['pages', 'activePage', 'dropdowns'],
}
</script>


<style scoped>
.active {
    text-decoration: underline;
}

nav {
    background-color: black !important;
    color: white !important;
    border-radius: 0 0 7px 7px !important;
}

* {
    color: red !important;
}

#logo {
    width: 100px;
    height: 50px;
}
</style>