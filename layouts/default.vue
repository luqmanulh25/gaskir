<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer" app>
      <Sidebar />
    </v-navigation-drawer>

    <v-app-bar app style="background:#4A4A4A;color:#ffff">
      <v-app-bar-nav-icon @click="drawer = !drawer" style="color:#ffff">
        <v-icon size="40" class="hidden-xs-only">mdi-chevron-left</v-icon>
        <v-icon
          size="30"
          class="hidden-xl-only hidden-md-only hidden-lg-and-up "
          >mdi-menu</v-icon
        >
      </v-app-bar-nav-icon>

      <v-toolbar-title class="hidden-xs-only">Sembunyikan Menu</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-col md="2" class="d-xl-flex mt-7 d-xs-flex" sm="2">
        <v-select
          background-color="#ffff"
          :items="items"
          v-model="select"
          dense
          outlined
        ></v-select>
      </v-col>

      <!-- <v-select
        class="mt-6"
        background-color="#ffff"
        :items="items"
        v-model="select"
        dense
        outlined
      ></v-select> -->
      <v-btn dark color="amber" class="ml-2 mr-5">
        <v-icon dark>
          mdi-plus
        </v-icon>
      </v-btn>

      <v-avatar>
        <img src="https://cdn.vuetifyjs.com/images/john.jpg" alt="John" />
      </v-avatar>

      <div class="mt-5 ml-5 hidden-xs-only">
        <h3>Luqmanul Hakim</h3>
        <p>Super Admin</p>
      </div>
    </v-app-bar>

    <v-main>
      <v-container fluid>
        <Nuxt />
      </v-container>
    </v-main>

    <v-footer padless style="background:#ffff">
      <v-col class="text-center" cols="12">
        <div class="d-flex justify-center align-center">
          <v-img src="logo.png" max-width="200"></v-img>
          <strong>Copyright 2021</strong>
        </div>
      </v-col>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    drawer: null,
    select: "Jakarta",
    items: ["Jakarta", "Bandung", "Depok", "Bogor"]
  })
};
</script>

<style>
.container {
  background: #f1f3f4;
}
</style>
