<template>
  <Navbar />
  <main>
    <!-- banner -->
    <section class="hero" id="hero">
      <div class="container py-3 py-lg-5">
        <div class="row">
          <div class="col-lg-6 mx-auto">
            <img src="@/assets/logo.webp" alt="Logo do evento" class="img-fluid">
            <p class="text-center fs-2 text-principal fw-semibold">
              No dia 06 de agosto, das 8 às 18h
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- sobre -->
    <section id="about">
      <div class="container py-3 py-lg-5">
        <h1 class="fw-bold text-center text-principal">
          17º Workshop Internacional Endoscopia Digestiva
        </h1>
        <div class="row">
          <div class="col-lg-9 mx-auto">
            <p class="text-center">
              O maior evento mineiro da área do Aparelho Digestivo contará com renomados especialistas de Minas Gerais,
              do Brasil e do exterior.
              <br>
              No dia 6 de agosto, durante o Gastrominas 2026, acompanhe uma programação exclusiva de casos ao vivo
              transmitidos diretamente do Instituto Alfa de Gastroenterologia do HC-UFMG, com a apresentação de técnicas
              avançadas e discussões conduzidas por referências da especialidade.
              <br>
              Serão mais de 15 procedimentos ao vivo, proporcionando uma experiência única de aprendizado e atualização
              científica.
              <br>
              Faça sua inscrição em <a href="https://gastrominas.com.br" target="_blank" rel="noopener noreferrer"
                class="text-principal fw-semibold">gastrominas.com.br</a> e participe deste grande
              encontro da gastroenterologia.
            </p>
            <p class="text-center">
              <button class="btn btn-danger btn-lg fs-5 rounded-4 px-5 py-2" @click="subscribe">
                INSCREVA-SE AGORA
              </button>
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- participantes -->
    <section id="speakers">
      <div class="container py-3 py-lg-5">
        <h1 class="fw-bold text-center text-principal">
          Participantes
        </h1>
        <div class="row">
          <div class="col-lg-9 mx-auto">
            <div class="row justify-content-center">
              <div class="col-lg-4" v-for="speaker in speakers" :key="speaker.id">
                <div class="p-3">
                  <img :src="speaker.image" :alt="'Imagem de ' + speaker.name"
                    class="img-fluid rounded-pill d-block mx-auto">
                  <p class="mb-0 text-center fw-semibold">
                    {{ speaker.name }}
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- programação -->
    <section id="schedule" class="bg-principal">
      <div class="container py-3 py-lg-5">
        <h1 class="fw-bold text-center text-light">
          Programação
        </h1>
        <div class="row">
          <div class="col-lg-9 mx-auto">
            <p class="fs-5 text-light text-center">
              Programação em breve
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- realização e organização -->
    <section id="realization">
      <div class="container py-3 py-lg-5">
        <h2 class="fw-bold text-center text-principal">
          Realização:
        </h2>
        <div class="row mb-3">
          <div class="col-lg-9 mx-auto">
            <div class="row">
              <div class="col-6 col-md-4 col-lg-3 align-self-center" v-for="realization in realizations"
                :key="realization.id">
                <div class="p-3">
                  <img :src="realization.image" :alt="'Imagem de ' + realization.name"
                    class="img-fluid d-block mx-auto">
                </div>
              </div>
            </div>
          </div>
        </div>

        <h2 class="fw-bold text-center text-principal">
          Organização:
        </h2>
        <div class="row mb-3">
          <div class="col-6 col-md-4 col-lg-3 mx-auto">
            <img :src="core" alt="Imagem da CORE Eventos" class="img-fluid d-block mx-auto">
          </div>
        </div>

      </div>
    </section>
  </main>
  <Footer />
</template>

<script setup lang="ts">
import Navbar from '@/components/NavbarComponent.vue';
import Footer from '@/components/FooterComponent.vue';
//palestrantes
import rodrigo from '@/assets/rodrigo.jpg';
//realização
import gastrominas from '@/assets/gastrominas.png';
import amg from '@/assets/amg.png';
import sobedmg from '@/assets/sobedmg.png';
import smc from '@/assets/sociedade_mineira.png';
import core from '@/assets/core.png';

const subscribe = () => {
  window.open('https://gastrominas.com.br/2026/inscricao', '_blank');
}

const speakers = [
  { id: 1, name: 'Rodrigo Roda R. da Silva', image: rodrigo },
];

const realizations = [
  { id: 1, name: 'Gastrominas', image: gastrominas },
  { id: 2, name: 'AMG', image: amg },
  { id: 3, name: 'SobeDMG', image: sobedmg },
  { id: 4, name: 'Sociedade Mineira', image: smc }
];

</script>

<style scoped>
.hero {
  background-image: url('@/assets/bg.webp');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}
</style>