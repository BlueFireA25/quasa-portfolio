<template>
  <q-page class="q-pa-none">
    <HomeProfile id="home" />
    <AboutProfile id="about" />
    <SkillsProfile id="skills" />
  </q-page>
</template>

<script setup lang="ts">
import HomeProfile from 'components/HomeProfile.vue';
import AboutProfile from 'components/AboutProfile.vue';
import SkillsProfile from 'components/SkillsProfile.vue';
</script>
