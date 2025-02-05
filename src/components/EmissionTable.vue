<script setup>
import { ref } from 'vue';
import emissionData from "@/assets/emissionData.json";
import CompanyFilter from './CompanyFilter.vue';

const data = ref(emissionData);
const countries = Array.from(new Set(emissionData.map(a => a.country))).sort();
const currentlySelectedCountries = ref([]);
const currentlySelectedCompany = ref('');
const sorting = ref('lth-company');

function checkCountry(company) {
    return currentlySelectedCountries.value.includes(company.country);
}

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
        data.value = emissionData.filter(checkCountry);
    } else {
        data.value = emissionData;
    }
    if (currentlySelectedCompany.value !== '') {
        data.value = data.value.filter((company) => company.name === currentlySelectedCompany.value);
    }
    console.log("doing stuff");
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
                <div class="dropdown col d-flex justify-content-start">
                    <button class="btn btn-primary dropdown-toggle align-self-center" type="button" data-bs-toggle="dropdown"
                        aria-expanded="false">
                        <span>Nach Ländern filtern</span>
                    </button>
                    <ul class="list-unstyled dropdown-menu">
                        <li v-for="country in countries" :key="country">
                            <div class="dropdown-item">
                                <input v-model="currentlySelectedCountries" type="checkbox" :id="country"
                                    :value="country" :index="country" />
                                <label :for="country" class="ps-2">{{ country }}</label>
                            </div>
                        </li>
                    </ul>
                </div>
                <div class="col-8">
                    <CompanyFilter v-model="currentlySelectedCompany"></CompanyFilter>
                </div>
            </div>
            <div class="row">
                <label class="col">
                    <span>Sortierung</span>
                    <select v-model="sorting" class="form-select" aria-label="Sortierung">
                        <option value="lth-company" selected>alphabetisch aufsteigend nach Unternehmen</option>
                        <option value="htl-company">alphabetisch absteigend nach Unternehmen</option>
                        <option value="lth-country">alphabetisch aufsteigend nach Land</option>
                        <option value="htl-country">alphabetisch absteigend nach Land</option>
                        <option value="lth-emissions">aufsteigend nach CO<sub>2</sub>-Emissionen</option>
                        <option value="htl-emissions">absteigend nach CO<sub>2</sub>-Emissionen</option>
                    </select>
                </label>
                <div class="col-3 d-flex justify-content-center">
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
                    <th>CO<sub>2</sub>-Emissionen in MtCO<sub>2</sub></th>
                </tr>
            </thead>
            <tbody id="emissions-table-body">
                <tr v-for="{ name, country, emissions } in data" :key="name">
                    <td>{{ name }}</td>
                    <td>{{ country }}</td>
                    <td>{{ parseFloat(emissions).toFixed(2) }}</td>
                </tr>
            </tbody>
        </table>
    </section>
</template>