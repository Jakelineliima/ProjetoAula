<template>
  <q-page>
    <q-card class="my-card">
      <q-img src="https://cdn.quasar.dev/img/chicken-salad.jpg" />

      <q-card-section>
        <q-btn
          fab
          color="primary"
          icon="place"
          class="absolute"
          style="top: 0; right: 12px; transform: translateY(-50%);"
        />

        <div class="row no-wrap items-center">
          <div class="col text-h6 ellipsis">
            Restaurante Pe de Fava
          </div>
          <div
            class="col-auto text-grey text-caption q-pt-md row no-wrap items-center"
          >
            <q-icon name="place" />
            Proximo
          </div>
        </div>

        <q-rating v-model="stars" :max="5" size="32px" />
      </q-card-section>

      <q-card-section class="q-pt-none">
        <div class="text-subtitle1">
          Rua Edimilson N° 445 Centro
        </div>
        <div class="text-caption text-grey">
          Servimos saladas, carnes de qualidade e suco natural<br />
        </div>
      </q-card-section>

      <q-separator />

      <q-card-actions>
        <q-btn flat round icon="event" />
        <q-btn outline color="primary">
          Reservar mesa
        </q-btn>
      </q-card-actions>
    </q-card>
  </q-page>
</template>
<script>
export default {
  data() {
    return {
      stars: 4
    };
  }
};
</script>
