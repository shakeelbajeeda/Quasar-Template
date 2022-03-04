<template>
  <q-list>
    <q-expansion-item
      expand-separator
      :icon="expansion_data.link_icon"
      :label="expansion_data.link_label"
      class="text-body1"
    >
      <q-item clickable tag="a" target="_self" :to="link" class="q-ml-md">
        <q-icon :name="expansion_data.expansion_data_link_icon" color="white" size="1.3rem" class="q-pl-sm" />

        <q-item-label class="text-body2 q-pl-md">{{expansion_data.expansion_data_link_label}}</q-item-label>
      </q-item>
    </q-expansion-item>
  </q-list>
</template>

<script>
export default {
  props: ["expansion_data"],
};
</script>
