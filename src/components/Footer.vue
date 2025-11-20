<template>
    <footer class="py-3 my-4">
        <ul class="nav justify-content-center border-bottom pb-3 mb-3">
            <li class="nav-item"><RouterLink to="/product" class="nav-link px-2 text-body-secondary" >Products</RouterLink></li>
            <li class="nav-item"><RouterLink to="/about" class="nav-link px-2 text-body-secondary" >About</RouterLink></li>
            <li class="nav-item"><RouterLink to="/contact" class="nav-link px-2 text-body-secondary" >Contact</RouterLink></li>
        </ul>
        <p class="text-center text-body-secondary">© 2025 Nuimbase mechanics, Inc</p>
    </footer>
</template>

<style>
.nav-link:hover {
    color: #c28b00 !important;
    transform: scale(1.05)
}
</style>