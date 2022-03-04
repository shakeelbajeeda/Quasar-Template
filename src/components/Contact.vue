<template>
  <q-item clickable v-ripple>
    <q-item-section avatar>
      <q-avatar
        :color="contact_data.color"
        :text-color="contact_data.text_color"
      >
        <img :src="contact_data.src" alt="" />
      </q-avatar>
    </q-item-section>
    <q-item-section>
      <q-item-label>{{ contact_data.contact_name }}</q-item-label>
      <q-item-label caption>{{ contact_data.contact_profession }}</q-item-label>
    </q-item-section>
    <q-item-section
    side
    :class="$q.screen.lt.sm ? 'message_icon_hide' : ''"
    >
      <q-btn icon="message" text-color="blue-7" flat round />
    </q-item-section>
    <q-item-section
    side
    :class="$q.screen.lt.sm ? 'message_icon_hide' : ''"
    >
      <q-btn icon="mail" text-color="red" flat round />
    </q-item-section>
    <q-item-section side>
      <q-btn icon="call" text-color="green" flat round />
    </q-item-section>
  </q-item>
</template>

<script>
export default {
  props: ["contact_data"],
};
</script>
