<script setup>
import { ref } from 'vue';

const isLTR = ref(getComputedStyle(document.body).direction === 'ltr' ? true : false);
import TextItem from './TextItem.vue';
import EmissionTable from './EmissionTable.vue';
import Sidebar from './Sidebar.vue'
</script>

<template>
  <Sidebar :alignLeft="isLTR"></Sidebar>
  <div class="container-fluid">
    <div class="row" :class="[isLTR ? 'justify-content-end' : 'justify-content-start']">
      <div class="col-10">
        <div class="container-fluid">
          <div class="row justify-content-center">
            <div class="col-11 col-md-9 col-lg-8 my-5">
              <section class="pt-4">
                <h1 class="m-3">Klimaschutz</h1>
                <figure>
                  <blockquote class="blockquote">
                    <p>Wir können eine Zukunft nicht akzeptieren, in der die Reichen in klimatisierten Blasen
                      geschützt sind, während der Rest der Menschheit von tödlichem Wetter in unbewohnbaren
                      Ländern heimgesucht wird. </p>
                  </blockquote>
                  <figcaption class="blockquote-footer">
                    UN-Generalsekretär António Guterres
                  </figcaption>
                </figure>
                <p class="lead">
                  Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt
                  ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo
                  dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor
                  sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor
                  invidunt ut labore et dolore
                </p>
              </section>


              <TextItem id="climatecrisis">
                <template #heading>Die Klimakrise</template>
                <p>
                  Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor
                  invidunt
                  ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo
                  duo
                  dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum
                  dolor
                  sit amet. Lorem ipsum dolor sit
                </p>
                <p>
                  Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor
                  invidunt
                  ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo
                  duo
                  dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum
                  dolor
                  sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod
                  tempor
                  invidunt ut
                </p>
              </TextItem>

              <EmissionTable></EmissionTable>

              <TextItem id="projects">
                <template #heading>Unsere Projekte</template>
                <p>
                  Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor
                  invidunt
                  ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo
                  duo
                  dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum
                  dolor
                  sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod
                  tempor
                  invidunt ut labore et dolore
                </p>
                <p>
                  Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor
                  invidunt
                  ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo
                  duo
                  dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum
                  dolor
                  sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod
                  tempor
                  invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam
                  et
                  justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem
                  ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam
                  nonumy
                  eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero
                  eos
                  et accusam et justo duo
                </p>
              </TextItem>

              <section class="container my-4" id="getactive">
                <div class="row">
                  <h2 class="mb-3">Werde aktiv</h2>
                  <div class="col-md-4">
                    <img src="@/assets/windmill.jpg" alt="Windrad" class="img-fluid">
                    <h2 class="fs-4 p-3">Informiere dich</h2>
                    <p>
                      Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod
                      tempor
                      invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et
                      accusam et
                      justo duo dolores et ea rebum. Stet clita kasd
                    </p>
                  </div>
                  <div class="col-md 4">
                    <img src="@/assets/demonstration.jpg" alt="Klima-Demonstration" class="img-fluid">
                    <h2 class="fs-4 p-3">Engangiere dich</h2>
                    <p>
                      Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod
                      tempor
                      invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et
                      accusam et
                      justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea
                    </p>
                  </div>
                  <div class="col-md-4">
                    <img src="@/assets/teamspirit.jpg" alt="Team" class="img-fluid">
                    <h2 class="fs-4 p-3">Schließe dich mit anderen zusammen</h2>
                    <p>
                      Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod
                      tempor
                      invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et
                      accusam et
                      justo duo dolores et ea rebum. Stet clita kasd gubergren.
                    </p>
                  </div>
                </div>
              </section>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
