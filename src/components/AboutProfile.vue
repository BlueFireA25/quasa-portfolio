<template>
  <div
    class="q-px-md container-section"
    data-aos="fade-down"
    data-aos-delay="100"
    data-aos-duration="1000"
  >
    <div class="column items-center q-mb-lg">
      <h3
        class="text-center text-h3 text-weight-medium text-dark q-pb-none q-mb-none"
      >
        {{ $t('about.title') }}
      </h3>
      <q-separator
        spaced
        inset
        class="q-pt-none q-mt-none"
        size="3px"
        style="width: 200px"
        color="primary"
      />
    </div>
    <p
      :class="`${
        Screen.xs ? 'text-center' : 'text-left'
      } text-body1 text-dark q-mb-lg`"
    >
      {{ $t('about.description') }}
    </p>
    <div
      :class="`${
        Screen.xs ? 'row items-center' : 'row items-start'
      } justify-between text-body1 q-col-gutter-y-md`"
    >
      <div
        class="col-auto col-xs-12 col-sm-6 column justify-center items-center text-dark"
      >
        <div
          :class="`${
            Screen.xs ? 'text-center' : 'text-start'
          } text-weight-medium text-h6 q-mb-md`"
        >
          {{ $t('about.personal-details') }}
        </div>
        <ul class="q-pa-none q-ma-none text-weight-medium q-gutter-y-md">
          <li>
            {{ $t('about.name') }}
            <span class="text-weight-regular">Sebastián Ibagué Castro</span>
          </li>
          <li>
            {{ $t('about.phone') }}
            <span class="text-weight-regular"
              ><span class="text-weight-medium">(+57)</span> 312 233 7092</span
            >
          </li>
          <li>
            Email:
            <span class="text-weight-regular"
              >sebastian.castroa25@gmail.com</span
            >
          </li>
          <li>
            {{ $t('about.languages') }}
            <span class="text-weight-regular">
              {{ $t('about.languages-description') }}
            </span>
          </li>
        </ul>
      </div>
      <div class="col-auto col-xs-12 col-sm-6 column">
        <div class="text-center text-weight-medium text-h6 text-dark">
          {{ $t('about.my-interests') }}
        </div>
        <div
          class="column justify-center items-center text-black q-gutter-y-md"
        >
          <div class="row justify-center q-gutter-md">
            <div
              class="column justify-center items-center interest-card bg-primary text-white"
            >
              <q-icon name="bi-airplane" size="25px" class="q-mb-sm" />
              <div class="text-body2">{{ $t('about.travel') }}</div>
            </div>
            <div
              class="column justify-center items-center interest-card bg-primary text-white"
            >
              <q-icon
                name="bi-journal-bookmark-fill"
                size="25px"
                class="q-mb-sm"
              />
              <div class="text-body2">{{ $t('about.read') }}</div>
            </div>
            <div
              class="column justify-center items-center interest-card bg-primary text-white"
            >
              <q-icon name="bi-music-player" size="25px" class="q-mb-sm" />
              <div class="text-body2">{{ $t('about.music') }}</div>
            </div>
          </div>
          <div class="row q-gutter-x-md q-gutter-y-md">
            <div
              class="column justify-center items-center interest-card bg-primary text-white"
            >
              <q-icon name="bi-controller" size="25px" class="q-mb-sm" />
              <div class="text-body2">{{ $t('about.games') }}</div>
            </div>
            <div
              class="column justify-center items-center interest-card bg-primary text-white"
            >
              <q-icon name="bi-camera-reels" size="25px" class="q-mb-sm" />
              <div class="text-body2">{{ $t('about.cinema') }}</div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="q-mt-xl text-center">
      <q-btn
        class="btn-cv"
        size="md"
        color="primary"
        icon-right="bi-file-earmark-arrow-down"
        :label="$t('about.download')"
        no-caps
        padding="24px"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import { Screen } from 'quasar';
</script>

<style scoped lang="scss">
.interest-card {
  width: 80px;
  height: 80px;
  border-radius: 25px;
  box-shadow: inset -8px 0px 18px 12px rgba(0, 0, 0, 0.1);
  transition: 0.2s all;
}

.interest-card:hover {
  transform: scale(1.07);
}

.btn-cv {
  border-radius: 16px;
  font-size: 18px !important;
  transition: 0.2s all;
  box-shadow: inset -8px 0px 18px 12px rgba(0, 0, 0, 0.1);
}

.btn-cv:hover {
  transform: translateY(-3.2px);
  transition: 0.3s;
}
</style>
