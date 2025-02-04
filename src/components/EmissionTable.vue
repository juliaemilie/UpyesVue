<script setup>
import emissionData from "@/assets/emissionData.json";
</script>

<template>
    <section class="my-4" id="co2emitters">
        <h2 class="mb-3">Die größten CO<sub>2</sub>-Emittenten</h2>
        <table class="table" id="emissions-table">
            <thead>
                <tr>
                    <th>Unternehmen</th>
                    <th>Land</th>
                    <th>CO<sub>2</sub>-Emissionen in MtCO<sub>2</sub></th>
                </tr>
            </thead>
            <tbody id="emissions-table-body">
                <tr v-for="{ name, country, emissions } in emissionData" :key="name">
                    <td>{{ name }}</td>
                    <td>{{ country }}</td>
                    <td>{{ emissions }}</td>
                </tr>
            </tbody>
        </table>
    </section>
</template>