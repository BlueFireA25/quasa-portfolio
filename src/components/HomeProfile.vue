<template>
  <div class="home column justify-center">
    <div
      class="home-content text-dark"
      data-aos="zoom-in"
      data-aos-delay="100"
      data-aos-duration="1000"
    >
      <div class="q-gutter-y-md">
        <h1 class="text-h2 text-weight-bold q-ma-none">
          Sebastián Ibagué Castro
        </h1>
        <p class="text-h5">
          I'm
          <span
            class="text-primary"
            id="typed-strings"
            data-typed-items="Designer, Developer, Freelancer, Photographer"
          ></span>
        </p>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { onMounted } from 'vue';
import Typed from 'typed.js';

onMounted(() => {
  typedEffect();
});

function typedEffect() {
  let typedContent = document.getElementById('typed-strings');
  if (typedContent) {
    let options = {
      strings: ['Frontend Developer', 'Systems Engineer'],
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

@media (min-width: 992px) {
  .home-content {
    padding-left: 160px;
  }
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
    font-size: 20px;
    line-height: 24px;
  }
}
</style>
