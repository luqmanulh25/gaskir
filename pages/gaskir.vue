<template>
  <v-cointainer>
    <h1>Tambah Petugas Parkir</h1>
    <v-row>
      <v-col sm="4">
        <v-card style="padding:20px">
          <h3>List Petugas Parkir</h3>
          <v-card v-for="(c, i) in cards" :key="i" class="mt-3">
            <v-list-item three-line>
              <v-list-item-avatar size="100">
                <v-avatar size="100">
                  <img :src="c.img" alt="John" />
                </v-avatar>
              </v-list-item-avatar>
              <v-list-item-content>
                <v-list-item-title class="text-h5 mb-1">
                  {{ c.name }}
                </v-list-item-title>
                <v-list-item-subtitle>{{ c.phone }}</v-list-item-subtitle>
                <v-list-item-subtitle>
                  <v-icon :color="c.status == 'Aktif' ? 'success' : ''"
                    >mdi-check-circle</v-icon
                  >
                  <span>{{ c.status }}</span>
                </v-list-item-subtitle>
              </v-list-item-content>
            </v-list-item>
          </v-card>
        </v-card>
      </v-col>
      <v-col>
        <v-card style="padding:20px" height="100%">
          <h3>Upload Document Data Diri</h3>

          <v-card style="padding:10px" class="mb-5 mt-4">
            <v-row>
              <v-col cols="12" md="6">
                <template>
                  <v-file-input
                    label="Upload KTP"
                    prepend-icon="mdi-camera"
                  ></v-file-input>
                </template>
                <span style="font-size:14px"
                  >Ekstensi file yang diperbolehkan :
                  <strong>JPEG,JPEG,PNG</strong>
                </span>
              </v-col>
              <v-col cols="12" md="6">
                <template>
                  <v-file-input
                    label="Upload Foto Diri"
                    prepend-icon="mdi-camera"
                  ></v-file-input>
                </template>
                <span style="font-size:14px"
                  >Ekstensi file yang diperbolehkan :
                  <strong>JPEG,JPEG,PNG</strong>
                </span>
              </v-col>
            </v-row>
          </v-card>
          <h3 class="mb-3">Informasi Lokasi Parkir</h3>
          <v-card>
            <v-form>
              <v-container style="background:#ffff">
                <v-row>
                  <v-col cols="12" md="6">
                    <v-text-field
                      v-model="nama"
                      label="Nama Petugas Parkir"
                      required
                    ></v-text-field>
                  </v-col>

                  <v-col cols="12" md="6">
                    <v-text-field
                      v-model="username"
                      label="Username"
                      required
                    ></v-text-field>
                  </v-col>
                  <v-col cols="12" md="6">
                    <v-text-field
                      v-model="nama"
                      label="NIK"
                      required
                    ></v-text-field>
                  </v-col>

                  <v-col cols="12" md="6">
                    <v-text-field
                      v-model="username"
                      label="Password"
                      required
                    ></v-text-field>
                  </v-col>
                  <v-col cols="12" md="6">
                    <v-text-field
                      v-model="username"
                      label="No.Telpon"
                      required
                    ></v-text-field>
                  </v-col>

                  <v-col cols="12" md="6">
                    <v-col cols="4">
                      <v-checkbox value label="Aktif"></v-checkbox>
                    </v-col>
                  </v-col>
                </v-row>
              </v-container>
            </v-form>
          </v-card>

          <div class="mt-10 mb-10 float-end">
            <v-btn color="error" outlined>Batal</v-btn>
            <v-btn color="orange" style="color:white">Simpan</v-btn>
          </div>
        </v-card>
      </v-col>
    </v-row>
  </v-cointainer>
</template>

<script>
export default {
  data() {
    return {
      selected: "a",
      cards: [
        {
          name: "Unggul",
          phone: "+6281726312",
          status: "Aktif",
          img: "https://cdn.vuetifyjs.com/images/john.jpg"
        },
        {
          name: "Hudya",
          phone: "+6281726312",
          status: "Aktif",
          img:
            "https://images.unsplash.com/photo-1535713875002-d1d0cf377fde?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=2000&q=80"
        },
        {
          name: "Esa Kencana",
          phone: "+6281726312",
          status: "Aktif",
          img:
            "https://www.microsoft.com/en-us/research/wp-content/uploads/2017/09/avatar_user_36443_1506533427.jpg"
        },
        {
          name: "Kusma Keling",
          phone: "+6281726312",
          status: "Aktif",
          img:
            "https://amzsummits.com/wp-content/uploads/2019/05/Ferry-Vermeulen.jpeg"
        },
        {
          name: "Dhimas Sujipto",
          phone: "+6281726312",
          status: "Aktif",
          img:
            "https://images.unsplash.com/photo-1527980965255-d3b416303d12?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1000&q=80"
        },
        {
          name: "Sumatja Alibaba",
          phone: "+6281726312",
          status: "Tidak Aktif",
          img: "https://ryansmetalroofing.com.au/images/user2.jpg"
        }
      ]
    };
  }
};
</script>
