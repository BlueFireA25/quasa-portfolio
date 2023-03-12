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
        Experience
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
    <q-tabs
      v-model="tab"
      dense
      class="text-grey"
      active-color="primary"
      indicator-color="primary"
      align="justify"
      narrow-indicator
    >
      <q-tab
        class="text-capitalize"
        name="work"
        label="Work"
        style="border-radius: 16px"
      />
      <q-tab
        class="text-capitalize"
        name="education"
        label="Education"
        style="border-radius: 16px"
      />
    </q-tabs>

    <q-tab-panels
      v-model="tab"
      animated
      class="text-dark"
      style="background: transparent"
    >
      <q-tab-panel name="work">
        <q-timeline
          :layout="layout"
          style="background: transparent"
          color="secondary"
        >
          <q-timeline-entry
            title="Frontend Developer"
            subtitle="May 2022 - Today"
            side="right"
            icon="bi-hospital-fill"
            color="cyan"
          >
            <div class="q-mb-md text-subtitle1 text-weight-medium">
              <div class="row items-center">
                <div
                  class="q-mr-sm bg-white q-pa-xs text-center"
                  style="border-radius: 50%"
                >
                  <q-img
                    src="~assets/img/logo-snabb.png"
                    :ratio="16 / 9"
                    width="30px"
                    height="30px"
                    fit="contain"
                    spinner-color="primary"
                    spinner-size="82px"
                    alt="logo-snabb"
                  />
                </div>
                <a href="https://snabb.cl/" target="_blank">Snabb</a>
              </div>
            </div>
            <ul>
              <li>Creation of new projects with Vue and Quasar.</li>
              <li>REST API consumption.</li>
              <li>Creation of Stores in Pinia.</li>
              <li>Creating components in Vue.</li>
              <li>FHIR documentation.</li>
            </ul>
          </q-timeline-entry>

          <q-timeline-entry
            title="Full Stack Developer"
            subtitle="February 2021 - February 2022"
            side="right"
            icon="bi-building-fill"
            color="blue"
          >
            <div class="q-mb-md text-subtitle1 text-weight-medium">
              <div class="row items-center">
                <div
                  class="q-mr-sm bg-white q-pa-xs text-center"
                  style="border-radius: 50%"
                >
                  <q-img
                    src="~assets/img/logo-binapps.png"
                    :ratio="16 / 9"
                    width="30px"
                    height="30px"
                    fit="contain"
                    spinner-color="primary"
                    spinner-size="82px"
                    alt="logo-snabb"
                  />
                </div>
                <a href="https://binapps.com/" target="_blank">Binapps</a>
              </div>
            </div>
            <ul>
              <li>Participation and creation of new web applications.</li>
              <li>
                Correction of errors and support in the different web
                applications of the company.
              </li>
              <li>Development of user interfaces.</li>
              <li>
                Implementation of new functions and features in its main ERP
                software and in the different developments of the company.
              </li>
              <li>Bug fixes and support in your core ERP software.</li>
            </ul>
          </q-timeline-entry>

          <q-timeline-entry
            title="Software Developer (Internship)"
            subtitle="August 2020 - February 2021"
            side="right"
            color="blue"
          >
            <div class="q-mb-md text-subtitle1 text-weight-medium">
              <div class="row items-center">
                <div
                  class="q-mr-sm bg-white q-pa-xs text-center"
                  style="border-radius: 50%"
                >
                  <q-img
                    src="~assets/img/logo-binapps.png"
                    :ratio="16 / 9"
                    width="30px"
                    height="30px"
                    fit="contain"
                    spinner-color="primary"
                    spinner-size="82px"
                    alt="logo-snabb"
                  />
                </div>
                <a href="https://binapps.com/" target="_blank">Binapps</a>
              </div>
            </div>
            <ul>
              <li>
                Implementation of new functions and features in its main ERP
                software and in the different developments of the company.
              </li>
              <li>Bug fixes and support in your core ERP software.</li>
            </ul>
          </q-timeline-entry>
        </q-timeline>
      </q-tab-panel>

      <q-tab-panel name="education">
        <q-timeline
          :layout="layout"
          style="background: transparent"
          color="secondary"
        >
          <q-timeline-entry
            title="Systems Engineer"
            subtitle="February 2021 - February 2022"
            side="right"
            icon="bi-mortarboard-fill"
            color="warning"
          >
            <div class="q-mb-md text-subtitle1 text-weight-medium">
              <div class="row items-center">
                <div
                  class="q-mr-sm bg-white q-pa-xs text-center"
                  style="border-radius: 50%"
                >
                  <q-img
                    src="~assets/img/logo-uam.jpg"
                    :ratio="16 / 9"
                    width="30px"
                    height="30px"
                    fit="contain"
                    spinner-color="primary"
                    spinner-size="82px"
                    alt="logo-snabb"
                  />
                </div>
                <a href="https://www.autonoma.edu.co/" target="_blank">
                  Universidad Autónoma de Manizales
                </a>
              </div>
            </div>
          </q-timeline-entry>

          <q-timeline-entry
            title="Other Studies"
            subtitle="All the time"
            side="right"
            icon="bi-hospital-fill"
            color="cyan"
          >
            <ul class="text-weight-medium">
              <li>
                <a
                  href="https://platzi.com/p/sebastian.castroa25/curso/2008-html-css/diploma/detalle/"
                  target="_blank"
                >
                  Curso Definitivo de HTML y CSS
                </a>
              </li>
              <li>
                <a
                  href="https://platzi.com/p/sebastian.castroa25/curso/2467-frontend-developer/diploma/detalle/"
                  target="_blank"
                >
                  Curso de Frontend Developer
                </a>
              </li>
              <li>
                <a
                  href="https://platzi.com/p/sebastian.castroa25/curso/2477-course/diploma/detalle/"
                  target="_blank"
                >
                  Curso Práctico de Frontend Developer
                </a>
              </li>
              <li>
                <a
                  href="https://www.udemy.com/certificate/UC-c9741149-7336-4c09-94ae-2e436c77e1ca/"
                  target="_blank"
                >
                  GIT + GitHub: Todo un sistema de control de versiones de cero,
                  Udemy
                </a>
              </li>
              <li>
                <a
                  href="https://www.udemy.com/certificate/UC-876a8867-d9e6-41d2-83c6-39ac05bc4427/"
                  target="_blank"
                >
                  Laravel 9 - Crea Aplicaciones y Sitios Web con PHP 8 y MVC,
                  Udemy
                </a>
              </li>
              <li class="q-pb-md">
                <a
                  href="https://www.freecodecamp.org/espanol/certification/BlueFire/responsive-web-design"
                  target="_blank"
                >
                  Responsive Web Design, Freecodecamp
                </a>
              </li>
            </ul>
            <q-btn
              href="https://www.linkedin.com/in/sebastianibaguecastro/"
              target="_blank"
              class="q-ml-lg"
              padding="14px 10px"
              style="border-radius: 16px"
              no-caps
              color="primary"
              icon="bi-linkedin"
              label="You can see all my courses on my LinkedIn."
            />
          </q-timeline-entry>
        </q-timeline>
      </q-tab-panel>
    </q-tab-panels>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';
import { useQuasar } from 'quasar';

const $q = useQuasar();
const layout = computed(() => {
  return $q.screen.lt.sm ? 'dense' : $q.screen.lt.md ? 'comfortable' : 'loose';
});
const tab = ref('work');
</script>
