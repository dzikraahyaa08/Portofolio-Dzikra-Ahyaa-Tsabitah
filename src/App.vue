<script setup>
// 1. Mengimpor file gambar dari folder src/public
import fotoProfil from './public/foto.jpg'

const portfolioItems = [
  {
    title: 'CafeResto App',
    tech: 'Android / Java / SQLite',
    image: 'https://picsum.photos/500/300?random=1',
    desc: 'Aplikasi pemesanan menu restoran dengan sistem login, registrasi, dan kalkulator harga otomatis.'
  },
  {
    title: 'Database Normalization',
    tech: 'MySQL / SQL',
    image: 'https://picsum.photos/500/300?random=2',
    desc: 'Perancangan ERD dan implementasi database dari tahap Master Bill hingga 3NF.'
  },
  {
    title: 'Max-Heap Project',
    tech: 'Java / NetBeans',
    image: 'https://picsum.photos/500/300?random=3',
    desc: 'Implementasi struktur data Max-Heap menggunakan Java untuk efisiensi pengolahan data.'
  }
]
</script>

<template>
  <v-app>
    <v-app-bar elevation="1" color="white">
      <v-container class="d-flex align-center">
        <v-toolbar-title class="font-weight-bold text-primary">PORTFOLIO.DZ</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn variant="text" href="#">Beranda</v-btn>
        <v-btn variant="text" href="#proyek">Proyek</v-btn>
      </v-container>
    </v-app-bar>

    <v-main class="bg-grey-lighten-4">
      <v-container>
        <v-row class="py-15" align="center">
          <v-col cols="12" md="7">
            <h2 class="text-h6 text-primary mb-2">Halo, Saya Dzikra Ahyaa Tsabitah</h2>
            <h1 class="text-h2 font-weight-black mb-4">Informatics Engineering Student</h1>
            <p class="text-body-1 text-grey-darken-1 mb-6">
              Saya berfokus dalam analisis data dan baru mulai mau terjun ke dunia web. Saya sangat antusias dalam belajar matematika dan logika.
            </p>
            <v-btn size="large" color="primary" elevation="2" class="px-8">Lihat Resume</v-btn>
          </v-col>

          <v-col cols="12" md="5" class="text-center">
            <v-avatar size="280" elevation="4" color="white">
              <v-img 
                :src="fotoProfil" 
                alt="Foto Profil Dzikra"
                cover
              >
                <template v-slot:placeholder>
                  <v-row class="fill-height ma-0" align="center" justify="center">
                    <v-progress-circular indeterminate color="primary"></v-progress-circular>
                  </v-row>
                </template>
              </v-img>
            </v-avatar>
          </v-col>
        </v-row>

        <h3 id="proyek" class="text-h4 font-weight-bold mb-8 text-center">Portofolio Pilihan</h3>
        <v-row>
          <v-col v-for="(item, index) in portfolioItems" :key="index" cols="12" sm="6" md="4">
            <v-card class="mx-auto h-100" hover elevation="2">
              <v-img height="200px" :src="item.image" cover></v-img>
              <v-card-item>
                <v-card-title>{{ item.title }}</v-card-title>
                <v-card-subtitle class="mt-1 text-primary">{{ item.tech }}</v-card-subtitle>
              </v-card-item>
              <v-card-text>{{ item.desc }}</v-card-text>
              <v-divider class="mx-4 mb-1"></v-divider>
              <v-card-actions>
                <v-btn color="primary" variant="text">Detail</v-btn>
                <v-btn color="secondary" variant="text" icon="mdi-github"></v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>

    <v-footer class="bg-grey-darken-4 text-center d-flex flex-column py-6">
      <div class="mb-2">© 2026 Dzikra - Informatics Engineering</div>
      <div class="d-flex">
        <v-btn icon="mdi-github" variant="text" color="white"></v-btn>
        <v-btn icon="mdi-instagram" variant="text" color="white"></v-btn>
        <v-btn icon="mdi-linkedin" variant="text" color="white"></v-btn>
      </div>
    </v-footer>
  </v-app>
</template>