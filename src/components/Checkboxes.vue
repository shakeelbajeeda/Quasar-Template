<template>
  <q-item>
    <q-checkbox v-model="val" class="text-white" />

    <q-item-section class="q-ml-md">
      <q-item-label>{{checkbox_data.title}}</q-item-label>
      <q-item-label caption>{{checkbox_data.caption}}</q-item-label>
    </q-item-section>
    <q-item-section side>
      <q-icon name="message" size="1.7rem" />
    </q-item-section>
  </q-item>
</template>

<script>
export default {
  props: ["checkbox_data"],
  data() {
    return {
      val: false
    }
  }
};

</script>
