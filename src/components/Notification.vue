<template>
  <q-item clickable v-ripple>
    <q-item-section avatar>
      <q-avatar
        :icon="notification_data.icon"
        :color="notification_data.color"
        :text-color="notification_data.text_color"
      />
    </q-item-section>
    <q-item-section>
      {{ notification_data.content }}
    </q-item-section>
  </q-item>
</template>

<script>
export default {
  props: ["notification_data"],
};
</script>
