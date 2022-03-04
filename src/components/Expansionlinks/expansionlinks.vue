<template>
  <q-list>
    <q-expansion-item
      expand-separator
      :icon="expansion_data.link_icon"
      :label="expansion_data.link_label"
      class="text-body1"
    >
      <ExpansionLinkDataVue
        v-for="newdata in linkdata"
        :key="newdata"
        :expansion_link_data="newdata"
      />
    </q-expansion-item>
  </q-list>
</template>

<script>
import { defineComponent } from "vue";
import ExpansionLinkDataVue from "src/components/Expansionlinks/expansionLinkData.vue";
export default {
  props: ["expansion_data"],
  components: { ExpansionLinkDataVue },
  data() {
    return {
      linkdata: [
        {
          expansion_data_link_icon: "mail",
          expansion_data_link_label: "Login"
        },
        {
          expansion_data_link_icon: "lock",
          expansion_data_link_label: "Lock Screen"
        },
        {
          expansion_data_link_icon: "lock",
          expansion_data_link_label: "Lock Screen-2"
        },
        {
          expansion_data_link_icon: "list",
          expansion_data_link_label: "Pricing",
          icon_heading: "Generic"
        },
        {
          expansion_data_link_icon: "person",
          expansion_data_link_label: "User Profile"
        },
        {
          expansion_data_link_icon: "settings",
          expansion_data_link_label: "Maintenance"
        },

      ],
    }
  }
};
</script>
