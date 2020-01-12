<template >
  <div id="game">
    <div v-if="prekidac">
      <div v-if="prekidac2">
        <Provjera v-on:load="Provjera" v-bind:niz="pogodci" v-bind:najvisePogodaka="najvisePogodaka" v-bind:glavna="glavna"/>
      </div>
      <div v-else>
        <Glkomb v-on:stolic="trollic"/>
      </div>
    </div>
    <div v-else>
      <Dodjela v-on:add-komb="addKomb" />
      <Counter v-on:load="Counter" />
    </div>
  </div>
</template>

<script>
import Dodjela from './../components/Gamelayout/Dodjela.vue';
import Counter from './../components/Counter.vue';
import Glkomb from './../components/Gamelayout/Glkomb.vue';
import Provjera from './../components/Gamelayout/Provjera.vue';

export default {
  name: 'Game',
  components:{
    Dodjela,
    Counter,
    Glkomb,
    Provjera,
  },
  data: function() {
    return {
      korKombinacije: [],
      prekidac: false,
      prekidac2: false,
      glavna: [],
      najvisePogodaka: 0,
      pogodci: [],
      zadnjiTiket: {},
      tiketi: 0,
    }
  },
  created() {
    var self = this;
    // Nakon 3 minute (60 sek) pokrenut će se funkcija getRezultat i promjeniti prekidac u false
    setTimeout(function() {
      self.getRezultat();
      self.prekidac = !self.prekidac;
    }, 60000);
    setTimeout(function() {
      self.prekidac2 = !self.prekidac2;
    }, 104000);
},

    methods:{
    addKomb:function(newKomb){
      this.korKombinacije.push(newKomb);
      this.zadnjiTiket = newKomb;
      this.tiketi++;
    },
    trollic:function(izvuceno){
      this.glavna.push(izvuceno);
    },
    getRezultat: function() {
      var niz = []; 
      var max = 0;
      var self = this;
      var korNiz = this.korKombinacije;
      var dobNiz = this.glavna;

      // Dodjeljujemo početne vrijednosti za 0 pogodaka, koje ćemo povećavati pri provjeri
      korNiz.forEach(function(){
        niz.push(0);
      });

      /* Za svaku korisničku kombinaciju provjeravat ćemo da li ima jednu od vrijednosti iz dobitne kombinacije
      Ukoliko ima povećavamo broj pogodaka u pomoćnom nizu broja sa indeksom tiketa kojeg provjeravamo */
      korNiz.forEach(function(obj, indeks){
        dobNiz.forEach(function(broj){
          if(obj.komb.includes(broj)){
            niz[indeks]++;
          }
        });
        if(niz[indeks] > max)
          max = niz[indeks];
      });

      this.najvisePogodaka = max;

      /* Uzimamo indeks iz pomoćnog niza svakog broja koji odgovara maksimalnom broju pogodaka
       I šaljemo nizu objekata koji se sastoji iz dobitnih tiketa */
      niz.forEach(function(broj, indeks){
        if(broj === max){
          self.pogodci.push(self.korKombinacije[indeks]);
        }
      });
    }
  }
}
</script>

<style>
</style>