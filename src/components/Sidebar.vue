<script setup>
defineProps(['alignLeft'])
</script>

<template>
    <div class="collapse navbar-collapse" id="side-navbar">
        <nav class="navbar light-green-background col-2-lg col-3 vh-100"
            :class="[alignLeft ? 'left-align' : 'right-align']" id="sidebar">
            <div class="d-flex black-green-color px-3">
                <div class="flex-column">
                    <div class="navbar-brand black-green-color" id="sidebar-label">Klimaschutz</div>   
                    <ul class="navbar-nav flex-column" id="main-nav">
                        <li class="nav-item py-2"><a class="nav-link" href="#climatecrisis"><i
                                    class="fa-solid fa-fire-flame-curved"></i> Die Klimakrise</a></li>
                        <li class="nav-item py-2"><a class="nav-link" href="/#co2emitters"><i
                                    class="fa-solid fa-smog"></i>
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
                </div>
            </div>
        </nav>
    </div>
</template>