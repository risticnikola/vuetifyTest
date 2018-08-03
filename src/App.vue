<template>
  <v-app>
    <v-navigation-drawer
      persistent
      :mini-variant="miniVariant"
      v-model="drawer"
      enable-resize-watcher
      fixed
      app
    >
      <v-list>
      <v-list-tile>
        <v-list-tile-action>
          <v-icon>home</v-icon>
        </v-list-tile-action>
        <v-list-tile-title>
          <router-link to="/">Home</router-link>
          </v-list-tile-title>
      </v-list-tile>
      <v-list-tile>
        <v-list-tile-action>
          <v-icon>question_answer</v-icon>
        </v-list-tile-action>
        <v-list-tile-title>
              <router-link to="/about">About</router-link>
              </v-list-tile-title>
      </v-list-tile>
      <v-list-group
        prepend-icon="account_circle"
        value="true"
      >
        <v-list-tile slot="activator">
          <v-list-tile-title>Users</v-list-tile-title>
        </v-list-tile>

        <v-list-group
          no-action
          sub-group
          value="true"
        >
          <v-list-tile slot="activator">
            <v-list-tile-title>Admin</v-list-tile-title>
          </v-list-tile>

          <v-list-tile  v-for="(admin, i) in admins" :key="i" >
            <v-list-tile-title v-text="admin[0]"></v-list-tile-title>
            <v-list-tile-action>
              <v-icon v-text="admin[1]"></v-icon>
            </v-list-tile-action>
          </v-list-tile>
        </v-list-group>

        <v-list-group sub-group no-action  >
          <v-list-tile slot="activator">
            <v-list-tile-title>Actions</v-list-tile-title>
          </v-list-tile>

          <v-list-tile v-for="(crud, i) in cruds" :key="i">
            <v-list-tile-title v-text="crud[0]"></v-list-tile-title>
            <v-list-tile-action>
              <v-icon v-text="crud[1]"></v-icon>
            </v-list-tile-action>
          </v-list-tile>
        </v-list-group>
      </v-list-group>
    </v-list>
    </v-navigation-drawer>
    <v-toolbar app>
      <!-- Menu button -->
      <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
      <!-- Page title -->
      <v-toolbar-title v-text="title"></v-toolbar-title>
      <v-spacer></v-spacer>
   
    </v-toolbar>
    <v-content>
      <router-view/>
    </v-content>
   
    <v-footer :fixed="fixed" app>
      <span>&copy; 2017</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data() {
    return {
      drawer: false,
      fixed: false,
      admins: [["Management", "people_outline"], ["Settings", "settings"]],
      cruds: [
        ["Create", "add"],
        ["Read", "insert_drive_file"],
        ["Update", "update"],
        ["Delete", "delete"]
      ],
      title: "Vuetify.js"
    };
  }
};
</script>
