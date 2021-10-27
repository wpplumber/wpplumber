<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated class="primary">
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
          WPPlumber
        </q-toolbar-title>

        <!-- <div>Quasar v{{ $q.version }}</div> -->
        <!--   Button component started here  -->

           <q-btn  flat>
            Support
            <q-icon name="settings"  size="sm" />
            <q-tooltip>Support</q-tooltip>
                  <q-menu  :offset="[10, 10]">

          <q-list style="min-width: 130px">

            <q-item clickable>
        <q-item-section>
          <q-icon name="summarize"  size="sm" />
        </q-item-section>
              <q-item-section>Wiki</q-item-section>
            </q-item>            
            <q-item clickable  >
        <q-item-section>
          <q-icon name="logout"  size="sm" />
        </q-item-section>
              <q-item-section>Feedback</q-item-section>
            </q-item>
          </q-list>

      </q-menu>
          </q-btn>

      </q-toolbar>
    </q-header>

<!--     <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
    >
      <q-list>
        <q-item-label
          header
        >
          Essential Links
        </q-item-label>

        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer> -->

      <q-footer reveal elevated class="bg-grey-6 ">
        <q-toolbar>
          <q-toolbar-title class="absolute-center">Copyright © 2021 </q-toolbar-title>
        </q-toolbar>
      </q-footer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
// import EssentialLink from 'components/EssentialLink.vue'

const linksList = [
  {
    title: 'Docs',
    caption: 'quasar.dev',
    icon: 'school',
    link: 'https://quasar.dev'
  },
  {
    title: 'Github',
    caption: 'github.com/quasarframework',
    icon: 'code',
    link: 'https://github.com/quasarframework'
  },
  {
    title: 'Discord Chat Channel',
    caption: 'chat.quasar.dev',
    icon: 'chat',
    link: 'https://chat.quasar.dev'
  },
  {
    title: 'Forum',
    caption: 'forum.quasar.dev',
    icon: 'record_voice_over',
    link: 'https://forum.quasar.dev'
  },
  {
    title: 'Twitter',
    caption: '@quasarframework',
    icon: 'rss_feed',
    link: 'https://twitter.quasar.dev'
  },
  {
    title: 'Facebook',
    caption: '@QuasarFramework',
    icon: 'public',
    link: 'https://facebook.quasar.dev'
  },
  {
    title: 'Quasar Awesome',
    caption: 'Community Quasar projects',
    icon: 'favorite',
    link: 'https://awesome.quasar.dev'
  }
];

import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'MainLayout',

  components: {
    // EssentialLink
  },

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      hello: false,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
})
</script>
