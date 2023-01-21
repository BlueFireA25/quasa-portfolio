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
          color="primary"
          outlined
          rounded
          v-model="lang"
          :options="langOptions"
          label="Language"
          dense
          borderless
          emit-value
          map-options
          options-dense
          bg-color="white"
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
import { ref, watch } from 'vue';
import { useI18n } from 'vue-i18n';
import { setCssVar, Screen, useQuasar } from 'quasar';
import languages from 'quasar/lang/index.json';
import MenuNavigation from 'components/MenuNavigation.vue';

const appLanguages = languages.filter((lang) =>
  ['es', 'en-US'].includes(lang.isoName)
);

const langOptions = appLanguages.map((lang) => ({
  label: lang.nativeName,
  value: lang.isoName,
}));

const $q = useQuasar();
const lang = ref($q.lang.isoName);
const { locale } = useI18n({ useScope: 'global' });

watch(lang, (val) => {
  // dynamic import, so loading on demand only
  import(
    /* webpackInclude: /(es|en-US)\.js$/ */
    'quasar/lang/' + val
  ).then((lang) => {
    $q.lang.set(lang.default);
    locale.value = lang.default.isoName;
  });
});

const themeStatus = ref(false);

function changeTheme(status: boolean) {
  if (status) {
    setCssVar('primary', '#0563bb');
    setCssVar('dark', '#242a2f');
    document.body.style.setProperty('background-color', '#fff');
    themeStatus.value = false;
  } else {
    setCssVar('primary', '#23b924');
    setCssVar('dark', '#fff');
    document.body.style.setProperty('background-color', '#1f2326');
    themeStatus.value = true;
  }
}
</script>

<style scoped>
.container {
  padding-top: 0 !important;
}
</style>
