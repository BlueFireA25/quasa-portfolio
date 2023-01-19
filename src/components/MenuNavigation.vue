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
      Screen.md ? headerMobileNavActive : ''
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
        name="mails"
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
          <div class="q-ml-lg">Home</div>
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
          <div class="q-ml-lg">About</div>
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
          <div class="q-ml-lg">Skills</div>
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
          <div class="q-ml-lg">Experience</div>
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
          <div class="q-ml-lg">Portfolio</div>
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
          <div class="q-ml-lg">Contact</div>
        </div>
      </q-tab>
    </q-tabs>
  </q-header>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import { scroll, Screen } from 'quasar';

const tab = ref('mails');
const { getScrollTarget, setVerticalScrollPosition } = scroll;
const headerMobileNavActive = ref('header-mobile-nav-active');
const navToggleIcon = ref('bi-list');
const navToggleActiveClass = ref('');

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
    background: #fff !important;
    border-right: 1px solid #e6e9ec;
    left: -300px;
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
  background-color: $accent;
  margin-bottom: 8px;
  width: 56px;
  height: 56px;
  border-radius: 50px !important;
  transition: 0.4s;
  text-transform: capitalize;
}

#header,
.nav-item:hover {
  width: 160px;
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
    background-color: $primary;
  }
}
</style>
