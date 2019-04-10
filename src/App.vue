<template>
  <v-app :dark="dark">
    <!-- <v-navigation-drawer
      v-model="primaryDrawer.model"
      :permanent="primaryDrawer.type === 'permanent'"
      :temporary="primaryDrawer.type === 'temporary'"
      :mini-variant="true"
      absolute
      overflow
      app
    >
      <v-list>
        <v-list-tile>
          <v-list-tile-title class="title">Application</v-list-tile-title>
        </v-list-tile>
      </v-list>

      <v-list dense class="pt-0">
        <v-list-tile v-for="item in myRoutes" :key="item.title">
          <v-list-tile-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>{{ item.title }}</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar :clipped-left="primaryDrawer.clipped" app absolute>
      <v-toolbar-side-icon
        v-if="primaryDrawer.type !== 'permanent'"
        @click.stop="primaryDrawer.model = !primaryDrawer.model"
      ></v-toolbar-side-icon>
      <v-toolbar-title>Mess Masi</v-toolbar-title>
    </v-toolbar> -->
    <v-content>
      <v-container fluid>
        <v-layout align-center justify-center>
          <!-- <v-flex xs10>
            <v-card>
              <v-card-text>
                <v-layout row wrap> -->
                  <router-view/>
                <!-- </v-layout>
              </v-card-text> -->
              <!-- <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn flat>Cancel</v-btn>
                <v-btn flat color="primary">Submit</v-btn>
              </v-card-actions> -->
            <!-- </v-card>
          </v-flex> -->
        </v-layout>
      </v-container>
    </v-content>
    <v-footer :inset="true" app>
      <span class="px-3">&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: "App",
  data: () => ({
    dark: true,
    drawers: ["Default (no property)", "Permanent", "Temporary"],
    primaryDrawer: {
      model: null,
      type: "default (no property)",
      clipped: true,
      floating: false,
      mini: true
    },
    // myRoutes: [
    //   { title: "Home", icon: "dashboard" },
    //   { title: "About", icon: "question_answer" }
    // ]
  })
};
</script>
