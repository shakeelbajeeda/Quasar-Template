<template>
  <q-item clickable v-ripple>
    <q-item-section avatar>
      <q-avatar
        :color="message_data.color"
        :text-color="message_data.text_color"
      >
        <img :src="message_data.src" alt="" />
      </q-avatar>
    </q-item-section>
    <q-item-section>
      <q-item-label>{{ message_data.contact_name }}</q-item-label>
      <q-item-label caption class="ellipsis">{{
        message_data.contact_message
      }}</q-item-label>
    </q-item-section>
    <q-item-section side>
      {{ message_data.message_time }}
    </q-item-section>
  </q-item>
</template>

<script>
export default {
  props: ["message_data"],
};
</script>
