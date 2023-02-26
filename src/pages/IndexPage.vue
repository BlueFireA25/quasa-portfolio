<template>
  <q-page class="q-pa-none">
    <HomeProfile class="q-mb-md" id="home" />
    <AboutProfile class="q-mb-xl" id="about" />
    <SkillsProfile class="q-mb-xl" id="skills" />
    <ExperienceProfile class="q-mb-xl" id="experience" />
    <PortfolioProfile class="q-mb-xl" id="portfolio" />
  </q-page>
</template>

<script setup lang="ts">
import HomeProfile from 'components/HomeProfile.vue';
import AboutProfile from 'components/AboutProfile.vue';
import SkillsProfile from 'components/SkillsProfile.vue';
import ExperienceProfile from 'components/ExperienceProfile.vue';
import PortfolioProfile from 'components/PortfolioProfile.vue';
</script>
