<script setup>
import { RouterLink, RouterView } from 'vue-router'
import 'bootstrap'
</script>

<template>  
  <header class="white-green-background sticky-top min-vh-10 shadow-sm">
        <nav class="navbar navbar-expand-sm">
            <div class="container-fluid">
                <a class="navbar-brand" href="#">
                    <img src="@/assets/logoPure.png" alt="Upyes Logo" width="50" class="d-inline-block align-text-top">
                    UPYES
                </a>
                <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav"
                    aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>
                <div class="collapse navbar-collapse justify-content-center">
                    <ul class="navbar-nav" id="header-nav">
                        <li class="nav-item"><RouterLink to="/" class="nav-link active" aria-current="page">Klimaschutz</RouterLink></li>
                        <li class="nav-item"><RouterLink to="/about" class="nav-link">Über uns</RouterLink></li>
                        <li class="nav-item"><RouterLink to="/contact" class="nav-link">Kontakt</RouterLink></li>
                    </ul>

                </div>

            </div>
        </nav>
    </header>

  <RouterView />
  <footer class="container-fluid black-green-background white-green-color">
        <nav>
            <ul class="nav justify-content-end" id="footer-nav">
                <li class="nav-item"><RouterLink to="/privacy" class="nav-link">Datenschutz</RouterLink></li>
                <li class="nav-item"><RouterLink to="/imprint" class="nav-link">Impressum</RouterLink></li>
            </ul>
        </nav>
    </footer>
</template>
