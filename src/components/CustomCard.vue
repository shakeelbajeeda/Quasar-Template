<template>
  <q-card
    class="my-card text-white"
    :style="'background:'+ card.bg_color"
  >
    <q-card-section>
      <div class="text-h6"> {{card.heading}}</div>
      <div class="text-subtitle2">{{card.title}}</div>
    </q-card-section>
    <q-card-section class="q-pt-none">
            {{card.content}}
    </q-card-section>
  </q-card>
</template>

<script>
export default {
  props : ['card']
};
</script>
