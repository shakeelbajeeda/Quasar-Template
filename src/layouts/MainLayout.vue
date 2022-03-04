<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title>
          Quasar App
        </q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      class="bg-dark text-white"
    >
      <q-list>
        <!-- <q-item-label
          header
        >
          Essential Links
        </q-item-label> -->

        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
        <expansionlinks
        v-for="expansion in expansions"
        :key="expansion"
        :expansion_data="expansion"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue';
import expansionlinks from 'src/components/Expansionlink/expansionlinks.vue';


const linksList = [
  {
    title: 'Dashboard',
    caption: '',
    icon: 'dashboard',
    link: '/dashboard'
  },
  {
    title: 'CRM Dashboard',
    caption: '',
    icon: 'dashboard',
    link: '/crm_dashboard'
  },
  {
    title: 'Pages',
    caption: '',
    icon: 'pages',
    link: 'https://chat.quasar.dev'
  },
  {
    title: 'Forum',
    caption: '',
    icon: 'record_voice_over',
    link: 'https://forum.quasar.dev'
  },
  {
    title: 'Twitter',
    caption: '',
    icon: 'rss_feed',
    link: 'https://twitter.quasar.dev'
  },
  {
    title: 'Facebook',
    caption: '',
    icon: 'public',
    link: 'https://facebook.quasar.dev'
  },
  {
    title: 'Quasar Awesome',
    caption: '',
    icon: 'favorite',
    link: 'https://awesome.quasar.dev'
  },
   {
    title: 'Facebook',
    caption: '',
    icon: 'public',
    link: 'https://facebook.quasar.dev'
  },
   {
    title: 'Facebook',
    caption: '',
    icon: 'public',
    link: 'https://facebook.quasar.dev'
  },


];

import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink,
    expansionlinks
  },

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  },
  data() {
    return {
      expansions: [
      {
        link_icon: "pages",
        link_label: "Pages",
        expansion_data_link_icon: "mail",
        expansion_data_link_label: "Login"
      },

      ]
    }
  }
})
</script>
