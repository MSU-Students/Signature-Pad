<template>
  <q-page class="page">
    <div class="row">
      <div class="col-6"></div>
      <div class="col-6 q-pt-xl ">
        <q-card bordered class="q-ml-xl q-mr-xl bg-amber">
          <q-card-section>
            <div class="text-h5 text-center q-mb-xl">SIGNATURE PAD</div>
          </q-card-section>

          <q-card-section >
            <q-input v-model="text" type="text" label="Name" />
          </q-card-section>
          <q-card-actions vertical>
            <q-btn class="bg-primary" label="LOGIN" />
          </q-card-actions>
          <q-space />
          <q-separator />
          <q-card-actions vertical>
            <q-btn class="bg-red" label="SIGN UP" />
          </q-card-actions>
        </q-card>
      </div>
    </div>
  </q-page>
</template>

<script lang="ts">
export default {};
</script>

<style scoped>
.page {
  background-image: url('~assets/BG.jpg');
}
</style>
