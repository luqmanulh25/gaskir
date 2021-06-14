<template>

  <v-list>
    <v-list-item>
      <v-img src="logo.png"></v-img>
    </v-list-item>
    <v-list-item
      link
      to="/"
    >
      <v-list-item-icon>
        <v-icon>mdi-view-dashboard</v-icon>
      </v-list-item-icon>

      <v-list-item-title>Dashboard</v-list-item-title>
    </v-list-item>

    <v-list-group
      v-for="item in items"
      :key="item.title"
      v-model="item.active"
      :prepend-icon="item.action"
      no-action
    >
      <template v-slot:activator>
        <v-list-item-content>
          <v-list-item-title v-text="item.title"></v-list-item-title>
        </v-list-item-content>
      </template>

      <v-list-item
        v-for="child in item.items"
        :key="child.title"
        link
        :to="child.link"
      >
        <v-list-item-content>
          <v-list-item-title v-text="child.title"></v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list-group>

    <v-list-item>
      <v-list-item-icon>
        <v-icon>mdi-account-circle</v-icon>
      </v-list-item-icon>

      <v-list-item-title>Sistem Admin</v-list-item-title>
    </v-list-item>
    <v-list-item>
      <v-list-item-icon>
        <v-icon>mdi-logout</v-icon>
      </v-list-item-icon>

      <v-list-item-title>Keluar</v-list-item-title>
    </v-list-item>
  </v-list>
</template>
<script>
export default {
  data: () => ({
    items: [
      {
        action: "mdi-text-box-multiple",
        url: "/gaskir",
        items: [
          { title: "Laporan Tarik" },
          { title: "Laporan Pendaftaran" },
          { title: "Pengaduan" },
          { title: "Laporan Member" },
          { title: "Laporan GasKir" },
          { title: "Laporan Aplikasi" },
        ],
        title: "Pelaporan",
      },
      {
        action: "mdi-cog",
        items: [
          { title: "Info Lokir" },
          { title: "Tarif" },
          { title: "GasKir", link: "/gaskir" },
          { title: "Shift" },
          { title: "Produk" },
          { title: "Pemutihan Kendaraan" },
          { title: "Aktivitasi Member" },
          { title: "Pengaturan Pengguna" },
        ],
        title: "Pengaturan Lokasi",
      },
      {
        action: "mdi-account",
        items: [
          { title: "Lokir" },
          { title: "Pengguna" },
          { title: "Hardware" },
        ],
        title: "Sistem Admin",
      },
    ],
  }),
};
</script>
