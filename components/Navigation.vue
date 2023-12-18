<template>
    <ul class="main-menu nav justify-content-center">
        <li>
            <nuxt-link to="/">Home</nuxt-link>
        </li>
        <li>
            <nuxt-link to="/about">About</nuxt-link>
        </li>
        <li class="has-submenu">
            <nuxt-link to="/service">Service</nuxt-link>

        </li>
        <li class="has-submenu">
            <nuxt-link to="/pack">Packs</nuxt-link>
        </li>
        <!-- <li class="has-submenu">
            <nuxt-link to="/project">Project</nuxt-link>
        </li> -->
        <li class="has-submenu">
            <nuxt-link to="/blog">Blog</nuxt-link>
        </li>
        <li>
            <nuxt-link to="/contact">Contact</nuxt-link>
        </li>
    </ul>
</template>