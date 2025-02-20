<script setup>
import { ref } from 'vue';
import emissionData from "@/assets/emissionData.json";

const data = ref(emissionData);
const countries = Array.from(new Set(emissionData.map(a => a.country))).sort();
const currentlySelectedCountries = ref([]);
const currentlySelectedCompany = ref('');
const sorting = ref('lth-company');

function compareStrings(a, b) {
    const nameA = a.toUpperCase(); // ignore upper and lowercase
    const nameB = b.toUpperCase(); // ignore upper and lowercase
    if (nameA < nameB) {
        return -1;
    }
    if (nameA > nameB) {
        return 1;
    }
    return 0;
}

function filterAndSort() {
    if (currentlySelectedCountries.value.length > 0) {
        data.value = emissionData.filter(company => currentlySelectedCountries.value.includes(company.country));
    } else {
        data.value = emissionData;
    }
    if (currentlySelectedCompany.value !== '') {
        data.value = data.value.filter(company => company.name === currentlySelectedCompany.value);
    }
    switch (sorting.value) {
        case 'htl-company':
            data.value.sort((a, b) => compareStrings(b.name, a.name));
            break;
        case 'lth-country':
            data.value.sort((a, b) => compareStrings(a.country, b.country));
            break;
        case 'htl-country':
            data.value.sort((a, b) => compareStrings(b.country, a.country));
            break;
        case 'lth-emissions':
            data.value.sort((a, b) => parseFloat(a.emissions) - parseFloat(b.emissions));
            break;
        case 'htl-emissions':
            data.value.sort((a, b) => parseFloat(b.emissions) - parseFloat(a.emissions));
            break;
        default:
            data.value.sort((a, b) => compareStrings(a.name, b.name));
    }
}
</script>

<template>
    <section class="my-4" id="co2emitters">
        <h2 class="mb-3">Die größten CO<sub>2</sub>-Emittenten</h2>
        <form class="container light-green-background my-5 p-4 rounded shadow-sm">
            <div class="row">
                <div class="dropdown col d-flex justify-content-start m-2">
                    <button class="btn btn-primary dropdown-toggle align-self-center" type="button" data-bs-toggle="dropdown"
                        aria-expanded="false">
                        <span>Nach Ländern filtern</span>
                    </button>
                    <ul class="list-unstyled dropdown-menu">
                        <li v-for="country in countries" :key="country">
                            <div class="dropdown-item">                                
                                <input v-model="currentlySelectedCountries" type="checkbox" :id="country" :value="country" :index="country"/>
                                <label :for="country" class="ps-2">{{ country }}</label>
                            </div>
                        </li>
                    </ul>
                </div>
                <div class="col m-2">
                    <span>Nach Unternehmen filtern</span>
                    <input class="form-control" v-model="currentlySelectedCompany" type="search" placeholder="z.B. Gazprom" maxlength="40">
                </div>
            </div>
            <div class="row">
                <label class="col m-2">
                    <span>Sortierung</span>
                    <select v-model="sorting" class="form-select">
                        <option value="lth-company" selected>alphabetisch aufsteigend nach Unternehmen</option>
                        <option value="htl-company">alphabetisch absteigend nach Unternehmen</option>
                        <option value="lth-country">alphabetisch aufsteigend nach Land</option>
                        <option value="htl-country">alphabetisch absteigend nach Land</option>
                        <option value="lth-emissions">aufsteigend nach CO2-Emissionen</option>
                        <option value="htl-emissions">absteigend nach CO2-Emissionen</option>
                    </select>
                </label>
                <div class="col-lg-3 d-flex justify-content-center m-2">
                    <button type="button" @click.prevent="filterAndSort"
                        class="btn btn-primary btn-lg align-self-end">Anwenden</button>
                </div>

            </div>
        </form>
        <table class="table my-4" id="emissions-table">
            <thead>
                <tr>
                    <th>Unternehmen</th>
                    <th>Land</th>
                    <th>CO<sub>2</sub>-Emissionen in MtCO<sub>2</sub>e</th>
                </tr>
            </thead>
            <tbody id="emissions-table-body">
                <tr v-for="{ name, country, emissions } in data" :key="name">
                    <td class="px-0 p-md-2">{{ name }}</td>
                    <td class="px-0 p-md-2">{{ country }}</td>
                    <td class="px-0 p-md-2">{{ parseFloat(emissions).toFixed(2) }}</td>
                </tr>
            </tbody>
        </table>
    </section>
</template>