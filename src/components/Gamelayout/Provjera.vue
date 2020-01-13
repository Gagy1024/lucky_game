<template>
  <div id="glavnakombinacija">
    <Header />
    <div id="komb">
            <p>Kombinacija igre je:</p>
            <button class="brojD" v-bind:key="'B' + broj" v-for="broj in glavna">{{broj}}</button>
            <hr>
        </div>
    <div id="kombinacije">
      <button class="ispis" v-bind:key="'a' + k" v-for="k in niz">{{k}}</button>
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