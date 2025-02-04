<script setup>
import { ref } from 'vue';
import emissionData from "@/assets/emissionData.json";
import CompanyFilter from './CompanyFilter.vue';

const data = ref(emissionData);
const countries = Array.from(new Set(emissionData.map(a => a.country))).sort();
const currentlySelectedCountries = ref([]);
const currentlySelectedCompany = ref('');

function checkCountry(company) {    
    return currentlySelectedCountries.value.includes(company.country);
}

function filter() {
    if (currentlySelectedCountries.value.length > 0) {
        data.value = emissionData.filter(checkCountry);
    } else {
        data.value = emissionData;
    }
    if (currentlySelectedCompany.value !== '') {
        console.log(data.value.filter((company) => company.name === currentlySelectedCompany.value));
        data.value = data.value.filter((company) => company.name === currentlySelectedCompany.value);
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
            <button @click.prevent="filter">Anwenden</button>
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
                    <td>{{ emissions }}</td>
                </tr>
            </tbody>
        </table>
    </section>
</template>