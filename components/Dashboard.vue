<template>
  <div>
    <h1>Dashboard</h1>
    <div class="d-md-flex justify-md-space-between">
      <v-card
        width="385"
        outlined
        style="border-radius:10px"
        v-for="(c, i) in cards"
        :key="i"
        class="mt-5 mx-auto mr-3"
      >
        <v-list-item three-line>
          <v-list-item-content>
            <v-list-item-title class="text-h5 mb-1">
              {{ c.title }}
            </v-list-item-title>
            <v-list-item-subtitle>
              <span :style="c.style" class="text--accent-1 ">{{
                c.subtitle
              }}</span>
            </v-list-item-subtitle>
          </v-list-item-content>

          <v-icon size="110" :color="c.icolor">{{ c.icon }}</v-icon>
        </v-list-item>

        <v-card-actions
          class="orange lighten-5 d-flex align-end "
          style="height:40px;margin-top:40px"
        >
          <span :style="c.fcolor">{{ c.footer }}</span>
        </v-card-actions>
      </v-card>
    </div>
    <div class="row mt-4 mb-4">
      <div class="col-md-6 ">
        <TotalPemasukanChart />
      </div>
      <div class="col-md-6">
        <MembershipChart />
      </div>
      <div class="col-md-6">
        <MetodePembayaranChart />
      </div>
      <div class="col-md-6">
        <TrafikSitusChart />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cards: [
        {
          title: "Kedatangan",
          subtitle: "2,500",
          icon: "mdi-arrow-left-thin-circle-outline",
          footer: "+30% dari minggu lalu",
          style: "font-size:32px;font-weight:bold;color:#66BB6A",
          fcolor: "color:#66BB6A",
          icolor: "#A5D6A7"
        },
        {
          title: "PJP Lama",
          subtitle: "2,000",
          icon: "mdi-backup-restore",
          footer: "+20% dari minggu lalu",
          style: "font-size:32px;font-weight:bold;color:#7E57C2",
          fcolor: "color:#66BB6A",
          icolor: "#D1C4E9"
        },
        {
          title: "PJP Baru",
          subtitle: "500",
          icon: "mdi-account-multiple-plus",
          footer: "-5% dari minggu lalu",
          style: "font-size:32px;font-weight:bold;color:#039BE5",
          fcolor: "color:#EF5350",
          icolor: "#B3E5FC"
        },
        {
          title: "PJP Lama",
          subtitle: "1,500",
          icon: "mdi-location-exit",
          footer: "-15% dari minggu lalu",
          style: "font-size:32px;font-weight:bold;color:#EF5350",
          fcolor: "color:#EF5350",
          icolor: "#FFCDD2"
        }
      ]
    };
  }
};
</script>
