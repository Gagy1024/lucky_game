<template>
  <div id="glavnakombinacija">
    <Header />
    <div id="komb">
            <p>Kombinacija igre je: {{glavna}}</p>
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