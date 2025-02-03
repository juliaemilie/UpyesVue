<template>
  <div class="d-flex">
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
              <img src="../assets/windmill.jpg" alt="Windrad" class="img-fluid">
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
              <img src="../assets/demonstration.jpg" alt="Klima-Demonstration" class="img-fluid">
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
              <img src="../assets/teamspirit.jpg" alt="Team" class="img-fluid">
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
