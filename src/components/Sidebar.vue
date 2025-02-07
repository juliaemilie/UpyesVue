<script setup>
import { ref, computed } from 'vue';

const props = defineProps(['alignLeft']);
const deviceHasSmallScreen = ref(window.innerWidth < 992);
const deviceHasBigScreen = ref(window.innerWidth >= 992);
const sidebarVisible = ref(deviceHasBigScreen.value);

function handleWindowSizeChange() {
    deviceHasSmallScreen.value = (window.innerWidth < 992);
    deviceHasBigScreen.value = (window.innerWidth >= 992);
    sidebarVisible.value = deviceHasBigScreen.value;
}
window.addEventListener('resize', handleWindowSizeChange);

const sidebarAlignment = computed(() => ({
    'justify-content-start': deviceHasSmallScreen.value || (!deviceHasSmallScreen.value && props.alignLeft),
    'justify-content-end': !deviceHasSmallScreen.value && !props.alignLeft
}))

function toggleSidebar() {
    sidebarVisible.value = !sidebarVisible.value;
}
</script>

<template>
    <div class="container fixed-top ms-0 mt-5" :class="{ 'vw-20 vh-100' : deviceHasBigScreen }">
        <div class="row mt-5" :class="[alignLeft ? 'justify-content-start' : 'justify-content-end']">
            <button v-if="deviceHasSmallScreen" @click="toggleSidebar" class="btn btn-secondary m-4 mb-0 shadow-sm" type="button" id="sidebar-button">
                <i class="fa-solid fa-bars"></i>
            </button>
        </div>
        <div class="row vh-100" v-if="sidebarVisible">
            <nav class="col-10 col-sm-8 col-lg-10 navbar vh-50 light-green-background rounded m-4 mt-0 p-4 shadow-sm" :class="sidebarAlignment">
                <div class="navbar-brand black-green-color d-none d-lg-block" id="sidebar-label">Klimaschutz</div>
                <ul class="navbar-nav" id="main-nav">
                    <li class="nav-item py-2" @click="toggleSidebar"><a class="nav-link" href="#climatecrisis"><i
                                class="fa-solid fa-fire-flame-curved"></i> Die Klimakrise</a></li>
                    <li class="nav-item py-2" @click="toggleSidebar"><a class="nav-link" href="/#co2emitters"><i class="fa-solid fa-smog"></i>
                            Die größten CO<sub>2</sub>-Emittenten</a>
                    </li>
                    <li class="nav-item py-2" @click="toggleSidebar"><a class="nav-link" href="#projects"><i
                                class="fa-solid fa-diagram-project"></i>
                            Unsere Projekte</a></li>
                    <li class="nav-item py-2" @click="toggleSidebar">
                        <a class="nav-link" href="/#getactive"><i class="fa-solid fa-people-group"></i>
                            Werde aktiv</a>
                    </li>
                </ul>

            </nav>
        </div>
    </div>
</template>