<template>
  <div id="glavnakombinacija">
    <Header />
    <div id="komb">
            <p>Kombinacija igre je:</p>
            <button class="brojD" v-bind:key="'B' + broj" v-for="broj in glavna">{{broj}}</button>
            <hr>
        </div>
    

        <div class="a" v-if="!niz.length">Nema dobitaka!!!</div>

        <div class="a" v-else>Najviše pogodaka: {{najvisePogodaka}}</div><hr>

        <div class="dobitak" v-bind:key="tiket.idtiketa" v-for="tiket in niz">
            <p>Broj tiketa: {{tiket.idtiketa}}</p>
            <button class="broj" v-bind:key="'A' + broj" v-for="broj in tiket.kombinacija">{{broj}}</button>
            <hr>
        </div>
    </div>
</template>

<script>
import Header from './../layout/Header';

export default {
  name: 'Provjera',
  components: {
    Header
  },
  props: ['niz', 'najvisePogodaka', 'glavna']
    }



//var korNiz = this.tiketKombinacije;
//var dobNiz = this.konacniniz;
//var brojPogodaka = 0;
//var pogodci = [];
/*
this.tiketKombinacije.forEach(function(x){
  if(this.konacniniz.includes(x)){
    this.pogodci.push(x);
    this.brojPogodaka++;
  }});
}}}
*/
 
</script>

<style scoped>

</style>