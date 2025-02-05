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
        <form>
            <fieldset id="country">
                <legend>Länder</legend>
                <ul>
                    <li v-for="country in countries" :key="country">
                        <input v-model="currentlySelectedCountries" type="checkbox" :id="country" :value="country"
                            :index="country" />
                        <label :for="country">{{ country }}</label>
                    </li>
                </ul>
            </fieldset>
            <CompanyFilter v-model="currentlySelectedCompany"></CompanyFilter>
            <label>
                Sortierung:
                <select v-model="sorting">
                    <option value="lth-company">alphabetisch aufsteigend nach Unternehmen</option>
                    <option value="htl-company">alphabetisch absteigend nach Unternehmen</option>
                    <option value="lth-country">alphabetisch aufsteigend nach Land</option>
                    <option value="htl-country">alphabetisch absteigend nach Land</option>
                    <option value="lth-emissions">aufsteigend nach CO<sub>2</sub>-Emissionen</option>
                    <option value="htl-emissions">absteigend nach CO<sub>2</sub>-Emissionen</option>
                </select>
            </label>
            <button @click.prevent="filterAndSort">Anwenden</button>
        </form>
        <table class="table" id="emissions-table">
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