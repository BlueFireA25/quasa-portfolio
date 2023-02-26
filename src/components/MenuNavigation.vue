<template>
  <q-page-sticky
    class="z-max mobile-nav-toggle"
    position="top-right"
    :offset="[10, 10]"
  >
    <q-btn
      :class="navToggleActiveClass"
      flat
      round
      color="dark"
      :icon="navToggleIcon"
      size="md"
      @click="
        navToggleIcon == 'bi-list'
          ? ((navToggleIcon = 'bi-x'),
            (navToggleActiveClass = 'mobile-nav-active'),
            openNav(true),
            scrollHidden())
          : ((navToggleIcon = 'bi-list'),
            (navToggleActiveClass = ''),
            openNav(false),
            scrollHidden())
      "
    />
  </q-page-sticky>
  <q-header
    elevated
    id="header"
    :class="`bg-transparent overflow-hidden fixed ${
      Screen.md || Screen.lg || Screen.xl ? headerMobileNavActive : ''
    }`"
  >
    <q-tabs
      v-model="tab"
      vertical
      class="text-black q-pl-md"
      indicator-color="transparent"
      active-bg-color="primary"
      active-color="white"
      align="center"
    >
      <q-tab
        class="nav-item"
        name="home"
        @click="
          scrollToElement('home'),
            openNav(false),
            (navToggleIcon = 'bi-list'),
            (navToggleActiveClass = '');
          scrollHidden();
        "
      >
        <div class="row items-center self-start" style="margin-left: 10px">
          <q-icon name="bi-house-door" size="23px" />
          <div class="q-ml-lg">{{ $t('menu.home') }}</div>
        </div>
      </q-tab>

      <q-tab
        class="nav-item"
        name="about"
        @click="
          scrollToElement('about'),
            openNav(false),
            (navToggleIcon = 'bi-list'),
            (navToggleActiveClass = '');
          scrollHidden();
        "
      >
        <div class="row items-center self-start" style="margin-left: 10px">
          <q-icon name="bi-person" size="23px" />
          <div class="q-ml-lg">{{ $t('menu.about') }}</div>
        </div>
      </q-tab>

      <q-tab
        class="nav-item"
        name="skills"
        @click="
          scrollToElement('skills'),
            openNav(false),
            (navToggleIcon = 'bi-list'),
            (navToggleActiveClass = '');
          scrollHidden();
        "
      >
        <div class="row items-center self-start" style="margin-left: 10px">
          <q-icon name="bi-file-earmark-code" size="23px" />
          <div class="q-ml-lg">{{ $t('menu.skill') }}</div>
        </div>
      </q-tab>

      <q-tab
        class="nav-item"
        name="experience"
        @click="
          scrollToElement('experience'),
            openNav(false),
            (navToggleIcon = 'bi-list'),
            (navToggleActiveClass = '');
          scrollHidden();
        "
      >
        <div class="row items-center self-start" style="margin-left: 10px">
          <q-icon name="bi-journal-check" size="23px" />
          <div class="q-ml-lg">{{ $t('menu.experience') }}</div>
        </div>
      </q-tab>

      <q-tab
        class="nav-item"
        name="portfolio"
        @click="
          scrollToElement('portfolio'),
            openNav(false),
            (navToggleIcon = 'bi-list'),
            (navToggleActiveClass = ''),
            openNav(false),
            (navToggleIcon = 'bi-list'),
            (navToggleActiveClass = '');
          scrollHidden();
        "
      >
        <div class="row items-center self-start" style="margin-left: 10px">
          <q-icon name="bi-archive" size="23px" />
          <div class="q-ml-lg">{{ $t('menu.portfolio') }}</div>
        </div>
      </q-tab>

      <q-tab
        class="nav-item"
        name="contact"
        @click="
          scrollToElement('contact'),
            openNav(false),
            (navToggleIcon = 'bi-list'),
            (navToggleActiveClass = '');
          scrollHidden();
        "
      >
        <div class="row items-center self-start" style="margin-left: 10px">
          <q-icon name="bi-phone" size="23px" />
          <div class="q-ml-lg">{{ $t('menu.contact') }}</div>
        </div>
      </q-tab>
    </q-tabs>
  </q-header>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue';
import { scroll, Screen } from 'quasar';

const tab = ref('home');
const { getScrollTarget, setVerticalScrollPosition } = scroll;
const headerMobileNavActive = ref('header-mobile-nav-active');
const navToggleIcon = ref('bi-list');
const navToggleActiveClass = ref('');
const home = ref<DOMRect>();
const about = ref<DOMRect>();
const skills = ref<DOMRect>();
const experience = ref<DOMRect>();
const portfolio = ref<DOMRect>();

window.onscroll = function () {
  let y = window.scrollY;

  if (
    home.value &&
    about.value &&
    skills.value &&
    experience.value &&
    portfolio.value
  ) {
    if (y === home.value.top && y < about.value.top) {
      tab.value = 'home';
    }
    if (y >= about.value.top && y < skills.value.top) {
      tab.value = 'about';
    }
    if (y >= skills.value.top && y < experience.value.top) {
      tab.value = 'skills';
    }
    if (y >= experience.value.top && y < portfolio.value.top) {
      tab.value = 'experience';
    }
    if (y >= portfolio.value.top) {
      tab.value = 'portfolio';
    }
  }
  return window.scrollY;
};

onMounted(() => {
  let elementHome = document.getElementById('home') as HTMLElement;
  let rectHome = elementHome.getBoundingClientRect();
  home.value = rectHome;

  let elementAbout = document.getElementById('about') as HTMLElement;
  let rectAbout = elementAbout.getBoundingClientRect();
  about.value = rectAbout;

  let elementSkills = document.getElementById('skills') as HTMLElement;
  let rectSkills = elementSkills.getBoundingClientRect();
  skills.value = rectSkills;

  let elementExperience = document.getElementById('experience') as HTMLElement;
  let rectExperience = elementExperience.getBoundingClientRect();
  experience.value = rectExperience;

  let elementPortfolio = document.getElementById('portfolio') as HTMLElement;
  let rectPortfolio = elementPortfolio.getBoundingClientRect();
  portfolio.value = rectPortfolio;
});

function openNav(active: boolean) {
  let header = document.getElementById('header');
  if (header) {
    header.style.left = active ? '0' : '-300px';
  }
}

function scrollToElement(id: string) {
  let el = document.getElementById(id);
  if (el) {
    const target = getScrollTarget(el);
    const offset = el.offsetTop + 3;
    const duration = 900;
    setVerticalScrollPosition(target, offset, duration);
  }
}

function scrollHidden() {
  if (navToggleActiveClass.value == 'mobile-nav-active') {
    document.body.classList.add('mobile-body');
  } else {
    document.body.classList.remove('mobile-body');
  }
}
</script>

<style scoped lang="scss">
/*--------------------------------------------------------------
# Header
--------------------------------------------------------------*/
#header {
  top: 0;
  bottom: 0;
  transition: all 0.5s;
  width: 200px !important;
}

.header-mobile-nav-active {
  left: 0 !important;
}

@media (max-width: $breakpoint-sm-max) {
  #header {
    width: 300px !important;
    background-color: var(--q-white) !important;
    box-shadow: rgba(0, 0, 0, 0.16) 0px 1px 4px, var(--q-dark) 0px 0px 0px 3px;
    left: -300px;
  }
}

@media (max-width: $breakpoint-xs-max) {
  #header {
    width: 250px !important;
  }
}

/*--------------------------------------------------------------
# Navigation Menu
--------------------------------------------------------------*/
/*--------------------------------------------------------------
# Desktop Navigation
--------------------------------------------------------------*/
.q-tabs :nth-child(1) {
  display: flex !important;
  flex-direction: column !important;
}

.nav-item {
  background-color: var(--q-accent);
  margin-bottom: 8px;
  width: 56px;
  height: 56px;
  border-radius: 50px !important;
  transition: all 0.4s;
  text-transform: capitalize;
}

.nav-item:hover {
  width: 160px;
  background-color: var(--q-primary);
  color: white;
}

.nav-item :nth-child(2) :nth-child(1) {
  width: 20px !important;
  height: 20px !important;
}

.q-tab--active {
  display: inline;
}

.q-tab--active:not(:hover) div:nth-child(2) {
  display: none;
}

.q-tab--inactive {
  display: inline;
}

.q-tab--inactive:hover div:nth-child(2) {
  display: block;
}

.q-tab--inactive div:nth-child(2) {
  display: none;
}

/*--------------------------------------------------------------
# Mobile Navigation
--------------------------------------------------------------*/

.mobile-nav-toggle {
  transform: none !important;
  transition: all 0.4s;
  display: none;
}

@media (max-width: $breakpoint-sm-max) {
  .nav-item {
    width: 90%;
  }

  .nav-item:hover {
    width: 90%;
  }

  .q-tab--active:not(:hover) div:nth-child(2),
  .q-tab--inactive div:nth-child(2) {
    display: block;
  }

  .mobile-nav-toggle {
    display: block;
  }

  .mobile-nav-active {
    color: #fff !important;
    background-color: var(--q-primary);
  }
}
</style>
