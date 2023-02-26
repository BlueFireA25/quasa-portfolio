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
        Skills
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
    <div class="row q-col-gutter-y-xl">
      <div class="col-sm-12 q-pl-md">
        <q-expansion-item
          class="my-card-1 q-pa-none"
          group="frontend"
          icon="bluetooth"
          label="Fourth"
          header-class="bg-primary text-white"
          expand-icon-class="text-white"
          default-opened
        >
          <q-card>
            <q-card-section>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quidem,
              eius reprehenderit eos corrupti commodi magni quaerat ex numquam,
              dolorum officiis modi facere maiores architecto suscipit iste
              eveniet doloribus ullam aliquid. Lorem ipsum dolor sit amet,
              consectetur adipisicing elit. Quidem, eius reprehenderit eos
              corrupti commodi magni quaerat ex numquam, dolorum officiis modi
              facere maiores architecto suscipit iste eveniet doloribus ullam
              aliquid. Lorem ipsum dolor sit amet, consectetur adipisicing elit.
              Quidem, eius reprehenderit eos corrupti commodi magni quaerat ex
              numquam, dolorum officiis modi facere maiores architecto suscipit
              iste eveniet doloribus ullam aliquid.
            </q-card-section>
          </q-card>
        </q-expansion-item>
      </div>
      <div class="col-xs-12 col-sm-6 q-pl-md">
        <q-expansion-item
          class="my-card-2 q-pa-none"
          group="design"
          icon="bluetooth"
          label="Fourth"
          header-class="bg-primary text-white"
          expand-icon-class="text-white"
          default-opened
        >
          <q-card>
            <q-card-section>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quidem,
              eius reprehenderit eos corrupti commodi magni quaerat ex numquam,
              dolorum officiis modi facere maiores architecto suscipit iste
              eveniet doloribus ullam aliquid.
            </q-card-section>
          </q-card>
        </q-expansion-item>
      </div>
      <div class="col-xs-12 col-sm-6 q-pl-md">
        <q-expansion-item
          class="my-card-3 q-pa-none"
          group="backend"
          icon="bluetooth"
          label="Fourth"
          header-class="bg-primary text-white"
          expand-icon-class="text-white"
          default-opened
        >
          <q-card>
            <q-card-section>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quidem,
              eius reprehenderit eos corrupti commodi magni quaerat ex numquam,
              dolorum officiis modi facere maiores architecto suscipit iste
              eveniet doloribus ullam aliquid.
            </q-card-section>
          </q-card>
        </q-expansion-item>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.my-card-1 {
  box-shadow: rgba(var(--q-shadow), 0.4) -5px 5px,
    rgba(var(--q-shadow), 0.3) -10px 10px, rgba(var(--q-shadow), 0.2) -15px 15px,
    rgba(var(--q-shadow), 0.1) -20px 20px,
    rgba(var(--q-shadow), 0.05) -25px 25px, rgba(var(--q-shadow), 0.4) 5px 5px,
    rgba(var(--q-shadow), 0.3) 10px 10px, rgba(var(--q-shadow), 0.2) 15px 15px,
    rgba(var(--q-shadow), 0.1) 20px 20px, rgba(var(--q-shadow), 0.05) 25px 25px;
}

.my-card-2 {
  box-shadow: rgba(var(--q-shadow), 0.4) -5px 5px,
    rgba(var(--q-shadow), 0.3) -10px 10px, rgba(var(--q-shadow), 0.2) -15px 15px,
    rgba(var(--q-shadow), 0.1) -20px 20px,
    rgba(var(--q-shadow), 0.05) -25px 25px;
  border: 3px solid rgba(var(--q-shadow), 0.6);
}

.my-card-3 {
  box-shadow: rgba(var(--q-shadow), 0.4) 5px 5px,
    rgba(var(--q-shadow), 0.3) 10px 10px, rgba(var(--q-shadow), 0.2) 15px 15px,
    rgba(var(--q-shadow), 0.1) 20px 20px, rgba(var(--q-shadow), 0.05) 25px 25px;
  border: 3px solid rgba(var(--q-shadow), 0.6);
}
</style>
