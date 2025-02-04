<script setup>
import TextItem from './TextItem.vue';
import EmissionTable from './EmissionTable.vue';
</script>

<template>
  <div class="d-flex">
    <nav class="light-green-background col-md-3 col-lg-2 navbar navbar-expand-md sticky-top vh-100" id="sidebar">
      <div class="d-flex black-green-color px-2">
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav"
          aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse flex-column">
          <div class="navbar-brand">Klimaschutz</div>
          <ul class="navbar-nav flex-column" id="main-nav">
            <li class="nav-item py-2"><a class="nav-link" href="#climatecrisis"><i
                  class="fa-solid fa-fire-flame-curved"></i> Die Klimakrise</a></li>
            <li class="nav-item py-2"><a class="nav-link" href="#co2emitters"><i class="fa-solid fa-smog"></i> Die
                größten
                CO<sub>2</sub>-Emittenten</a>
            </li>
            <li class="nav-item py-2"><a class="nav-link" href="#projects"><i class="fa-solid fa-diagram-project"></i>
                Unsere Projekte</a></li>
            <li class="nav-item py-2"><RouterLink to="/#getactive" class="nav-link"><i class="fa-solid fa-people-group"></i>
                Werde aktiv</RouterLink></li>
          </ul>

        </div>

      </div>
    </nav>

    <div class="my-4 px-5" id="content">
      <div class="container-fluid col-md-8 justify-content-center">
        <h1>Klimaschutz</h1>
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

        <TextItem>
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

        <TextItem>
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
              <h2>Informier dich</h2>
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
              <h2>Engangiere dich</h2>
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
              <h2>Schließe dich mit anderen zusammen</h2>
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
</template>
