<template>
  <div class="home column justify-center">
    <div
      class="home-content text-dark text-center"
      data-aos="zoom-in"
      data-aos-delay="100"
      data-aos-duration="1000"
    >
      <div
        :class="`${Screen.lg || Screen.xl ? 'row' : 'column column reverse'} ${
          Screen.lg || Screen.xl ? 'justify-center' : 'justify-start'
        } items-center`"
      >
        <div class="q-pa-none q-ma-none">
          <h1 class="text-h2 text-weight-bold q-mt-none">
            Sebastián Ibagué Castro
          </h1>
          <p class="text-h5">
            {{ $t('home.hello') }}
            <span class="text-primary" id="typed-strings"></span>
            <span class="text-primary" id="typed-strings"></span>
          </p>
        </div>

        <svg
          :class="`${Screen.lg || Screen.xl ? 'q-mb-xl q-ml-xs' : ''} `"
          version="1.1"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 500 500"
          :width="
            Screen.lg || Screen.xl
              ? '450px'
              : Screen.md || Screen.sm
              ? '300px'
              : '300px'
          "
          id="blobSvg"
          style="opacity: 1"
        >
          <image
            x="-30"
            y="25"
            width="100%"
            height="100%"
            clip-path="url(#shape)"
            href="../assets/img/profile.png"
            preserveAspectRatio="none"
          ></image>
          <defs>
            <linearGradient id="gradient" x1="0%" y1="0%" x2="0%" y2="100%">
              <stop offset="0%" style="stop-color: rgb(238, 205, 163)"></stop>
              <stop offset="100%" style="stop-color: rgb(239, 98, 159)"></stop>
            </linearGradient>
          </defs>
          <clipPath id="shape">
            <path id="blob" fill="url(#gradient)">
              <animate
                attributeName="d"
                dur="10000ms"
                repeatCount="indefinite"
                values="M440.5,320.5Q418,391,355.5,442.5Q293,494,226,450.5Q159,407,99,367Q39,327,31.5,247.5Q24,168,89,125.5Q154,83,219.5,68Q285,53,335.5,94.5Q386,136,424.5,193Q463,250,440.5,320.5Z;M453.78747,319.98894Q416.97789,389.97789,353.96683,436.87838Q290.95577,483.77887,223.95577,447.43366Q156.95577,411.08845,105.64373,365.97789Q54.33169,320.86732,62.67444,252.61056Q71.01719,184.3538,113.01965,135.21007Q155.02211,86.06634,220.52211,66.46683Q286.02211,46.86732,335.5,91.94472Q384.97789,137.02211,437.78747,193.51106Q490.59704,250,453.78747,319.98894Z;M411.39826,313.90633Q402.59677,377.81265,342.92059,407.63957Q283.24442,437.46649,215.13648,432.5428Q147.02853,427.61911,82.23325,380.9572Q17.43796,334.29529,20.45223,250.83809Q23.46649,167.38089,82.5856,115.05707Q141.70471,62.73325,212.19045,63.73015Q282.67618,64.72705,352.67308,84.79839Q422.66998,104.86972,421.43486,177.43486Q420.19974,250,411.39826,313.90633Z;M440.5,320.5Q418,391,355.5,442.5Q293,494,226,450.5Q159,407,99,367Q39,327,31.5,247.5Q24,168,89,125.5Q154,83,219.5,68Q285,53,335.5,94.5Q386,136,424.5,193Q463,250,440.5,320.5Z;"
              ></animate>
            </path>
          </clipPath>
        </svg>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { onMounted } from 'vue';
import { useI18n } from 'vue-i18n';
import { Screen } from 'quasar';
import Typed from 'typed.js';

const i18n = useI18n();

onMounted(() => {
  typedEffect();
});

function typedEffect() {
  let typedContent = document.getElementById('typed-strings');
  if (typedContent) {
    let options = {
      strings: [i18n.t('home.title1'), i18n.t('home.title2')],
      typeSpeed: 70,
      backSpeed: 70,
      loop: true,
    };

    return new Typed('#typed-strings', options);
  }
}
</script>

<style scoped lang="scss">
.home {
  width: 100%;
  height: 100vh;
  background: url('../assets/img/background.jpg') top right no-repeat;
  background-size: cover;
  position: relative;
  padding: 60px 0;
  overflow: hidden;
}

.home:before {
  content: '';
  background: rgba(var(--q-white-rgb), 0.8);
  position: absolute;
  bottom: 0;
  top: 0;
  left: 0;
  right: 0;
}

@media (max-width: 992px) {
  .home-content {
    text-align: center;
  }

  .home-content .text-h2 {
    font-size: 32px;
  }

  .home-content p {
    margin-top: 10px;
    line-height: 24px;
  }

  .svg-image {
    align-self: center;
  }
}
</style>
