<script setup>
import NavContent from './NavContent.vue';
</script>

<template>
    <div>
        <nav class="navbar navbar-expand-sm" aria-label="Third navbar example" style="background-color: #FEFAE0;">
            <div class="container-fluid">

                <a class="navbar-brand" href="/">Nuim Mechanics</a>

                <button class="navbar-toggler" type="button" data-bs-toggle="collapse"
                    data-bs-target="#navbarsExample03">
                    <span class="navbar-toggler-icon"></span>
                </button>

                <div class="collapse navbar-collapse justify-content-center" id="navbarsExample03">
                    <ul class="navbar-nav mb-2 mb-sm-0 gap-2">

                        <li class="nav-item">
                            <RouterLink class="nav-link active" to="/product" style="color: black;">Products</RouterLink>
                        </li>

                        <li class="nav-item">
                            <RouterLink class="nav-link active" to="/about">About</RouterLink>
                        </li>

                        <li class="nav-item">
                            <RouterLink class="nav-link active" to="/contact">Contact</RouterLink>
                        </li>

                        <!-- <li class="nav-item dropdown">
                            <a class="nav-link dropdown-toggle" href="#" data-bs-toggle="dropdown">Services</a>

                            <ul class="dropdown-menu">
                                <li>
                                    <RouterLink class="dropdown-item" to="/interior">Interior</RouterLink>
                                </li>
                                <li>
                                    <RouterLink class="dropdown-item" to="/furniture">Furnitures</RouterLink>
                                </li>
                                <li>
                                    <RouterLink class="dropdown-item" to="/other">Others</RouterLink>
                                </li>
                            </ul>
                        </li> -->

                    </ul>
                </div>
            </div>
        </nav>

        <div>
            <nav-content />
        </div>
    </div>
</template>

<style scoped>
nav.navbar {
    position: sticky;
    top: 0;
    z-index: 999;
}

/* Hover animation for nav links */
.nav-link {
    transition: color 0.3s ease, transform 0.3s ease;
}

.nav-link:hover {
    color: #c28b00 !important;
    transform: scale(1.05);
}

/* Dropdown hover */
.dropdown-item {
    transition: background-color 0.3s ease, padding-left 0.3s ease;
}

.dropdown-item:hover {
    background-color: #f1e4c1;
    padding-left: 10px;
}
</style>
