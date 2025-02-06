<script setup>
import { ref, computed } from 'vue';

const props = defineProps(['alignLeft']);
const deviceHasSmallScreen = ref(false);

function handleWindowSizeChange() {
    if (window.innerWidth < 992) {
        deviceHasSmallScreen.value = true;
    } else {
        deviceHasSmallScreen.value = false;
    }
}
window.addEventListener('resize', handleWindowSizeChange);

const classObject = computed(() => ({
    'justify-content-start': deviceHasSmallScreen.value || (!deviceHasSmallScreen.value && props.alignLeft),
    'justify-content-end': !deviceHasSmallScreen.value && !props.alignLeft
}))
</script>

<template>
    <div class="container fixed-top ms-0 mt-5 vh-100">
        <div class="row mt-5" :class="[alignLeft ? 'justify-content-start' : 'justify-content-end']">
            <button class="btn btn-secondary m-4 mb-0 d-lg-none" type="button" data-bs-toggle="collapse" data-bs-target="#side-navbar"
                aria-expanded="false" aria-controls="sidebar" id="sidebar-button">
                <i class="fa-solid fa-bars"></i>
            </button>
        </div>
        <div class="row vh-100" :class="classObject">
            <nav class="col-lg-2 col-10 navbar vh-50 light-green-background rounded m-4 mt-0 p-4" id="side-navbar">
                <div class="navbar-brand black-green-color d-none d-lg-block" id="sidebar-label">Klimaschutz</div>
                <ul class="navbar-nav" id="main-nav">
                    <li class="nav-item py-2"><a class="nav-link" href="#climatecrisis"><i
                                class="fa-solid fa-fire-flame-curved"></i> Die Klimakrise</a></li>
                    <li class="nav-item py-2"><a class="nav-link" href="/#co2emitters"><i class="fa-solid fa-smog"></i>
                            Die größten CO<sub>2</sub>-Emittenten</a>
                    </li>
                    <li class="nav-item py-2"><a class="nav-link" href="#projects"><i
                                class="fa-solid fa-diagram-project"></i>
                            Unsere Projekte</a></li>
                    <li class="nav-item py-2">
                        <a class="nav-link" href="/#getactive"><i class="fa-solid fa-people-group"></i>
                            Werde aktiv</a>
                    </li>
                </ul>

            </nav>
        </div>
    </div>
</template>