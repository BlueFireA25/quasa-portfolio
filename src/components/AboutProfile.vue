<template>
  <div class="text-center q-px-lg">
    <h3 class="text-h3 text-weight-medium text-dark">About Me</h3>
    <p class="text-body1 text-dark q-mb-lg">
      Frontend Developer and Systems Engineer, with knowledge of web
      technologies, programming languages and design. I am a responsible person
      with ease of working individually and as a team, always focused on
      developing quality software.
    </p>
    <div
      :class="`${
        Screen.xs ? 'column items-center' : 'row items-start'
      } justify-center text-body1 q-col-gutter-y-md`"
    >
      <div class="col-auto col-xs-12 col-sm-6 text-dark">
        <div class="text-weight-medium text-h6 q-mb-md">Personal Details</div>
        <ul class="q-pa-none q-ma-none text-weight-medium q-gutter-y-md">
          <li>
            Name:
            <span class="text-weight-regular">Sebastián Ibagué Castro</span>
          </li>
          <li>
            Phone:
            <span class="text-weight-regular">+57 312 233 7092</span>
          </li>
          <li>
            Email:
            <span class="text-weight-regular"
              >sebastian.castroa25@gmail.com</span
            >
          </li>
          <li>
            Language:
            <span class="text-weight-regular">Spanish - English (Middle)</span>
          </li>
        </ul>
      </div>
      <div class="col-auto col-xs-12 col-sm-6">
        <div class="text-weight-medium text-h6 text-dark">My interests</div>
        <div
          class="column justify-center items-center text-black q-gutter-y-md"
        >
          <div class="row justify-center q-gutter-x-md q-gutter-y-md">
            <div
              class="column justify-center items-center interest-card bg-primary text-white"
            >
              <q-icon name="bi-airplane" size="30px" class="q-mb-sm" />
              <div class="text-body1">Travel</div>
            </div>
            <div
              class="column justify-center items-center interest-card bg-primary text-white"
            >
              <q-icon
                name="bi-journal-bookmark-fill"
                size="30px"
                class="q-mb-sm"
              />
              <div class="text-body1">Read</div>
            </div>
            <div
              class="column justify-center items-center interest-card bg-primary text-white"
            >
              <q-icon name="bi-music-player" size="30px" class="q-mb-sm" />
              <div class="text-body1">Music</div>
            </div>
          </div>
          <div class="row q-gutter-x-md q-gutter-y-md">
            <div
              class="column justify-center items-center interest-card bg-primary text-white"
            >
              <q-icon name="bi-controller" size="30px" class="q-mb-sm" />
              <div class="text-body1">Games</div>
            </div>
            <div
              class="column justify-center items-center interest-card bg-primary text-white"
            >
              <q-icon name="bi-camera-reels" size="30px" class="q-mb-sm" />
              <div class="text-body1">Cinema</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { Screen } from 'quasar';
</script>

<style scoped lang="scss">
.interest-card {
  width: 100px;
  height: 100px;
  border-radius: 25px;
  box-shadow: inset -8px 0px 18px 12px rgba(0, 0, 0, 0.1);
  transition: all 0.2s;
}

.interest-card:hover {
  transform: scale(1.07);
}
</style>
