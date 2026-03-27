<script setup>
// 1. Mengimpor file gambar (Profil & Sertifikat Asli dari folder src)
import fotoProfil from './public/foto.jpg'
import imgSertifSeminar from './seminar.jpg' 
import imgSertifAnalisis from './dataanasis.jpg' 
import imgSertifIOT from './iot.jpg' 

const portfolioItems = [
  {
    title: 'CafeResto App',
    tech: 'Android / Java / SQLite',
    image: 'https://picsum.photos/500/300?random=1',
    desc: 'Aplikasi pemesanan menu restoran dengan sistem login, registrasi, dan kalkulator harga otomatis.',
    link: 'https://github.com/dzikrahayaa08' 
  },
  {
    title: 'Database Normalization',
    tech: 'MySQL / SQL',
    image: 'https://picsum.photos/500/300?random=2',
    desc: 'Perancangan ERD dan implementasi database dari tahap Master Bill hingga 3NF.',
    link: 'https://github.com/dzikrahayaa08'
  },
  {
    title: '🎮 Game Batu Gunting Kertas',
    tech: 'Java / Console App',
    image: 'https://picsum.photos/500/300?random=4',
    desc: 'Game sederhana berbasis Java dengan sistem input user dan random komputer.',
    link: 'https://github.com/dzikrahayaa08/game-batu-gunting-kertas'
  }
]

const certificates = [
  {
    title: 'Peserta Google Student Ambassador',
    issuer: 'Google',
    year: '2026',
    image: imgSertifSeminar 
  },
  {
    title: 'Database Design (3NF & ERD)',
    issuer: 'UIN Suska Riau',
    year: '2025',
    image: imgSertifAnalisis 
  },
  {
    title: 'Internet of Things (IoT) Workshop',
    issuer: 'UIN Suska Riau',
    year: '2025',
    image: imgSertifIOT
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
        <v-btn variant="text" href="#sertifikat">Sertifikat</v-btn>
      </v-container>
    </v-app-bar>

    <v-main class="bg-grey-lighten-4">
      <v-container>
        <v-row class="py-15" align="center">
          <v-col cols="12" md="7">
            <h2 class="text-h6 text-primary mb-2">Halo, Saya Dzikra Ahyaa Tsabitah</h2>
            <h1 class="text-h4 font-weight-black mb-4">
              Informatics Engineering Student Semester 4 Universitas Islam Negeri Sultan Syarif Kasim Riau
            </h1>
            <p class="text-body-1 text-grey-darken-1 mb-6">
              Saya berfokus dalam analisis data dan baru mulai mau terjun ke dunia web. Saya sangat antusias dalam belajar matematika dan logika.
            </p>
            <v-btn size="large" color="primary" elevation="2" class="px-8" href="#" target="_blank">
              Lihat Resume
            </v-btn>
          </v-col>

          <v-col cols="12" md="5" class="text-center">
            <v-avatar size="280" elevation="4" color="white">
              <v-img :src="fotoProfil" alt="Foto Profil Dzikra" cover>
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
            <v-card class="mx-auto h-100 d-flex flex-column" hover elevation="2" :href="item.link" target="_blank">
              <v-img height="200px" :src="item.image" cover></v-img>
              <v-card-item>
                <v-card-title>{{ item.title }}</v-card-title>
                <v-card-subtitle class="mt-1 text-primary">{{ item.tech }}</v-card-subtitle>
              </v-card-item>
              <v-card-text class="flex-grow-1">{{ item.desc }}</v-card-text>
              <v-divider class="mx-4 mb-1"></v-divider>
              <v-card-actions>
                <v-btn color="primary" variant="text" :href="item.link" target="_blank">Detail</v-btn>
                <v-spacer></v-spacer>
                <v-icon color="secondary" icon="mdi-github" class="mr-2"></v-icon>
              </v-card-actions>
            </v-card>
          </v-col>
        </v-row>

        <h3 id="sertifikat" class="text-h4 font-weight-bold mb-8 mt-15 text-center">Sertifikasi</h3>
        <v-row>
          <v-col v-for="(cert, i) in certificates" :key="i" cols="12" sm="6" md="4">
            <v-card variant="outlined" class="rounded-lg h-100 bg-white shadow-sm">
              <v-img :src="cert.image" height="180" cover class="bg-grey-lighten-2"></v-img>
              <v-card-item>
                <v-card-title class="text-subtitle-1 font-weight-bold">{{ cert.title }}</v-card-title>
                <v-card-subtitle class="text-primary">{{ cert.issuer }} • {{ cert.year }}</v-card-subtitle>
              </v-card-item>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>

    <v-footer class="bg-grey-darken-4 text-center d-flex flex-column py-6">
      <div class="mb-2">© 2026 Dzikra - Informatics Engineering</div>
      <div class="d-flex">
        <v-btn icon="mdi-github" variant="text" color="white" href="https://github.com/dzikrahayaa08" target="_blank"></v-btn>
        <v-btn icon="mdi-instagram" variant="text" color="white" href="#" target="_blank"></v-btn>
        <v-btn icon="mdi-linkedin" variant="text" color="white" href="#" target="_blank"></v-btn>
      </div>
    </v-footer>
  </v-app>
</template>

<style scoped>
.v-card {
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}
.v-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 10px 20px rgba(0,0,0,0.1) !important;
}
</style> 