<template>
  <div class="row">
    <div
      class="col-xs-3 col-md-4 col-sm-1 text-center"
      :class="box_data.icon_bg"
    >
      <q-avatar class="text-white" :icon="box_data.icon" square size="4rem">
      </q-avatar>
    </div>
    <div
      class="col-xs-9 col-md-8 col-sm-11 text-white"
      :class="box_data.content_bg"
    >
      <div class="q-ml-sm">
        <p class="text-h5 q-ma-none q-pt-sm">{{ box_data.amount }}</p>
        <p class="text-subtitle1 q-ma-none">{{ box_data.title }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["box_data"],
};
</script>
