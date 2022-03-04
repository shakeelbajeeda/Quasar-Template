<template>
  <q-item clickable tag="a" target="_self" :to="link" class="q-ml-md">
    <q-icon
      :name="expansion_link_data.expansion_data_link_icon"
      color="white"
      size="1.3rem"
      class="q-pl-sm"
    />
    <q-item-label class="text-body2 q-pl-md">{{ expansion_link_data.expansion_data_link_label }}</q-item-label>
  </q-item>
  <div class="text-bold q-pl-xl q-pb-sm">{{ expansion_link_data.icon_heading }}</div>
</template>

<script>
export default {
  props: ["expansion_link_data"],

}

</script>
