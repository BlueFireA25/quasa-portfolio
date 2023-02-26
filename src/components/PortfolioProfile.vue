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
        Portfolio
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
    <q-carousel
      swipeable
      animated
      v-model="slide"
      thumbnails
      infinite
      :autoplay="autoplay"
    >
      <q-carousel-slide
        :name="1"
        img-src="https://cdn.quasar.dev/img/mountains.jpg"
      />
      <q-carousel-slide
        :name="2"
        img-src="https://cdn.quasar.dev/img/parallax1.jpg"
      />
      <q-carousel-slide
        :name="3"
        img-src="https://cdn.quasar.dev/img/parallax2.jpg"
      />
      <q-carousel-slide
        class="bg-teal"
        :name="4"
        img-src="https://cdn.quasar.dev/img/quasar.jpg"
      >
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Magnam
        blanditiis, quod unde, cum dolorem inventore voluptatum esse non
        explicabo placeat distinctio, impedit quae facere magni exercitationem
        pariatur a vitae? Eligendi.</q-carousel-slide
      >

      <template v-slot:control>
        <q-carousel-control
          position="top-right"
          :offset="[18, 18]"
          class="text-white rounded-borders"
          style="background: rgba(0, 0, 0, 0.3); padding: 4px 8px"
        >
          <q-toggle
            dense
            dark
            color="orange"
            v-model="autoplay"
            label="Auto Play"
          />
        </q-carousel-control>
      </template>
    </q-carousel>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    return {
      slide: ref(1),
      autoplay: ref(false),
    };
  },
};
</script>
