<template>
  <q-layout view="lHh Lpr lFf">
    <q-page-sticky
      class="z-top"
      :offset="Screen.sm ? [30, 20] : Screen.xs ? [10, 20] : [16, 20]"
      position="bottom-left"
      style="transform: translateY(0)"
    >
      <div class="row justify-center items-center q-gutter-md">
        <q-select
          class="text-capitalize"
          color="primary"
          outlined
          rounded
          v-model="lang"
          :options="langOptions"
          :label="$t('menu.language')"
          dense
          borderless
          emit-value
          map-options
          options-dense
          bg-color="white"
          style="width: 200px"
        >
          <template v-slot:prepend>
            <q-icon name="bi-translate" color="primary" />
          </template>
        </q-select>
        <q-btn
          round
          color="white"
          :icon="`${themeStatus ? 'bi-sun-fill' : 'bi-moon-stars-fill'}`"
          size="13.334px"
          text-color="primary"
          @click="themeStatus ? changeTheme(true) : changeTheme(false)"
        />
      </div>
    </q-page-sticky>

    <MenuNavigation />
    <q-page-container class="container">
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup lang="ts">
import { ref, onMounted, watch } from 'vue';
import { useI18n } from 'vue-i18n';
import { setCssVar, Screen, useQuasar } from 'quasar';
import languages from 'quasar/lang/index.json';
import MenuNavigation from 'components/MenuNavigation.vue';
import AOS from 'aos';
import 'aos/dist/aos.css';
import Typed from 'typed.js';

AOS.init();

const appLanguages = languages.filter((lang) =>
  ['es', 'en-US'].includes(lang.isoName)
);

const langOptions = appLanguages.map((lang) => ({
  label: lang.nativeName,
  value: lang.isoName,
}));

const i18n = useI18n();
const $q = useQuasar();
const lang = ref($q.lang.isoName);
const { locale } = useI18n({ useScope: 'global' });
let a: Typed;

onMounted(() => {
  let options = typedEffect();
  if (options) {
    a = new Typed('#typed-strings', options);
  }
});

watch(lang, (val) => {
  // dynamic import, so loading on demand only
  import(
    /* webpackInclude: /(es|en-US)\.js$/ */
    'quasar/lang/' + val
  ).then((lang) => {
    $q.lang.set(lang.default);
    locale.value = lang.default.isoName;
    let options = typedEffect();

    if (options) {
      if (lang.default.isoName === 'en-US' || lang.default.isoName === 'es') {
        a?.destroy();
      }
      a = new Typed('#typed-strings', options);
    }
  });
});

const themeStatus = ref(false);

function changeTheme(status: boolean) {
  if (status) {
    setCssVar('primary', '#0563bb');
    setCssVar('dark', '#242a2f');
    document.body.style.setProperty('background-color', '#fff');
    document.body.style.setProperty('--q-white', '#fff');
    document.body.style.setProperty('--q-white-rgb', '255, 255, 255');
    themeStatus.value = false;
  } else {
    setCssVar('primary', '#23b924');
    setCssVar('dark', '#fff');
    document.body.style.setProperty('background-color', '#1f2326');
    document.body.style.setProperty('--q-white', '#1f2326');
    document.body.style.setProperty('--q-white-rgb', '0, 0, 0');
    themeStatus.value = true;
  }
}

function typedEffect() {
  let typedContent = document.getElementById('typed-strings');
  if (typedContent) {
    let options = {
      strings: [i18n.t('home.title1'), i18n.t('home.title2')],
      typeSpeed: 70,
      backSpeed: 70,
      loop: true,
    };

    return options;
  }
}
</script>

<style scoped>
.container {
  padding-top: 0 !important;
}
</style>
