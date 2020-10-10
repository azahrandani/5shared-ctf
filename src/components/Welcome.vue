<template>
  <div class="welcome container">
    <div class="text-center">
      <span class="welcome-text text-center">{{ welcomeText }}</span>
    </div>
    <div class="welcome-intro">
      <p class="text-center">Jadi ini ceritanya si Jahra mau nyoba bikinin game Catch The Flag buat kalian teman-teman tersayangnya <i class="fa fa-heart"></i></p>
      <p class="text-center">Catch The Flag itu kayak mainan para hacker buat mengasah kemampuan mereka.</p>
      <p class="text-center">TAPI JANGAN KHAWATIR! CTF ini levelnya yang cimit aja kok karena Ijah yang buat sendiri jadi ga akan seribet itu dan banyak main mainnya juga hueheuhe. Tapi beberapa langkah tetep butuh pengetahuan dasar kayak yang kita pelajari di pacil di semester-semester awal. Yakin deh pasti kalian mah bisa.</p>
      <p class="text-center">Di CTF, pemainnya harus ngumpulin <b>flag</b> yang tertulis dalam format tertentu.</p>
      <p class="text-center">Di 5Shared CTF ini, flag nya tertulis dalam format <b>5shared{sebuah-flag}</b>.</p>
      <p class="text-center">Jadi, kalian harus jeli ngeliat tulisan/string dalam format itu yes.</p>
      <p class="text-center">Ada 5 flag yang harus kalian temuin. Di akhirnya, kalian kumpulin semua flag itu dan kumpulin jadi satu string.</p>
      <p class="text-center">Nahh hasil string yang panjang itu nanti kalian taro di belakang url ini. Jadi nanti kalian ujung-ujungnya harus kunjungi <b>5shared-ctf.vercel.app/string-yang-dikumpulin</b> sebagai finish line kalian. Yeeeyy!</p>
      <p class="text-center">Semoga kalian suka dan enjoy mini CTF ini yaa. Good luck!</p>
    </div>
    <div class="text-center">
      <button type="button" class="btn btn-primary" data-toggle="modal" data-target="#marsModal">Let's go!</button>
    </div>
    <div class="modal fade" id="marsModal" tabindex="-1" role="dialog" aria-labelledby="marsModalLabel">
      <div class="modal-dialog modal-lg" role="document">
        <div class="modal-content">
          <div class="modal-header">
            <p class="modal-title" id="marsModalLabel"><b>Kita nyanyi mars fasilkom dulu yuk</b></p>
            <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
          </div>
          <div class="modal-body text-center mars-fasilkom">
            <div v-if="!successFirstMars">
              <p>Samudera laut ilmu <input v-model="terhampar"> di hadapanku</p>
              <p>Cakrawala <input v-model="bersinar"> memanggilku ke sana</p>
              <p>Kan ku sebrangi <input v-model="lautan"></p>
              <p>Tak ku <input v-model="kenal"> putus asa</p>
              <p>Dengan <input v-model="daya"> dan  <input v-model="upaya"></p>
              <p><input v-model="untuk"> ilmu komputer</p>
            </div>
            <div v-if="successFirstMars">
              <p>SAMUDERA LAUT ILMU <input v-model="terhamparCaps"> DI HADAPANKU</p>
              <p>CAKRAWALA <input v-model="bersinarCaps"> MEMANGGILKU KE SANA</p>
              <p>KAN KU SEBRANGI <input v-model="lautanCaps"></p>
              <p>TAK KU <input v-model="kenalCaps"> PUTUS ASA</p>
              <p>DENGAN <input v-model="dayaCaps"> DAN  <input v-model="upayaCaps"></p>
              <p><input v-model="untukCaps"> ILMU KOMPUTER</p>
            </div>
          </div>
          <div class="modal-footer">
            <p v-if="failFirstMars" style="color: red">Coba dicek lagi dek!</p>
            <p v-if="successFirstMars && !failSecondMars && !successSecondMars" style="color: green">KURANG KERAS MANA SUARANYA!</p>
            <p v-if="failSecondMars" style="color: red">MASIH ADA YANG BELUM HAPAL?! MANA SEMANGATNYA?</p>
            <p v-if="successSecondMars" style="color: green">OMEGA? 2016!</p>
            <button type="button" class="btn btn-primary" @click="checkMars">Udah ka!</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Typed from 'typed.js';

export default {
  name: 'Welcome',
  props: {
    msg: String
  },
  data () {
    return {
      'welcomeText': '',
      'showModal': false,
      'failFirstMars': false,
      'successFirstMars': false,
      'failSecondMars': false,
      'successSecondMars': false,
      'terhampar': '',
      'bersinar': '',
      'lautan': '',
      'kenal': '',
      'daya': '',
      'upaya': '',
      'untuk': '',
      'terhamparCaps': '',
      'bersinarCaps': '',
      'lautanCaps': '',
      'kenalCaps': '',
      'dayaCaps': '',
      'upayaCaps': '',
      'untukCaps': '',
    }
  },
  computed: {

  },
  methods: {
    typeWelcomeText () {
      new Typed('.welcome-text', {
        strings: [this.msg],
        typeSpeed: 60
      });
    },
    onClick () {
      this.showModal = true;
    },
    checkMars() {
      console.log('hah');
      if (!this.successFirstMars) {
        if (this.terhampar.toLowerCase() === 'terhampar'
          && this.bersinar.toLowerCase() === 'bersinar'
          && this.lautan.toLowerCase() === 'lautan'
          && this.kenal.toLowerCase() === 'kenal'
          && this.daya.toLowerCase() === 'daya'
          && this.upaya.toLowerCase() === 'upaya'
          && this.untuk.toLowerCase() === 'untuk') {
            this.successFirstMars = true;
            this.failFirstMars = false;
        } else {
          this.failFirstMars = true;
        }
      } else {
        if (this.terhamparCaps === 'TERHAMPAR'
          && this.bersinarCaps === 'BERSINAR'
          && this.lautanCaps === 'LAUTAN'
          && this.kenalCaps === 'KENAL'
          && this.dayaCaps === 'DAYA'
          && this.upayaCaps === 'UPAYA'
          && this.untukCaps === 'UNTUK') {
            this.successSecondMars = true;
            this.failSecondMars = false;
        } else {
          this.failSecondMars = true;
        }
      }
    }
  },
  mounted () {
    this.typeWelcomeText();
  }
}
</script>