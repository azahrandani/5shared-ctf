<template>
  <div class="welcome container">
    <h1 class="text-center">{{ msg }}</h1>
    <div class="welcome-intro">
      <p class="text-center">Jadi ini ceritanya si Jahra mau nyoba bikinin game Catch The Flag buat kalian teman-teman tersayangnya <i class="fa fa-heart"></i></p>
      <p class="text-center">Catch The Flag itu kayak mainan para hacker buat mengasah kemampuan mereka.</p>
      <p class="text-center">TAPI JANGAN KHAWATIR! CTF ini levelnya yang cimit banget kok karena Ijah yang buat sendiri jadi ga akan seribet itu hueheuhe.</p>
      <p class="text-center">Di CTF, pemainnya harus ngumpulin <b>flag</b> yang tertulis dalam format tertentu.</p>
      <p class="text-center">Di 5Shared CTF ini, flag nya tertulis dalam format <b>5shared{sebuah-flag}</b>.</p>
      <p class="text-center">Jadi, kalian harus jeli ngeliat tulisan/string dalam format itu yes.</p>
      <p class="text-center">Ada 5 flag yang harus kalian temuin. Di akhirnya, kalian kumpulin semua flag itu dan kumpulin jadi satu string.</p>
      <p class="text-center">Nahh hasil string yang panjang itu nanti kalian taro di belakang url ini. Jadi nanti kalian ujung-ujungnya harus kunjungi <b>5shared-ctf.vercel.app/string-yang-dikumpulin</b> sebagai finish line kalian. Yeeeyy!</p>
      <p class="text-center">Semoga kalian enjoy mini CTF ini yaa. Good luck!</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Welcome',
  props: {
    msg: String
  }
}
</script>