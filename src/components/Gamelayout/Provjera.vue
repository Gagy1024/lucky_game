<template>
  <div id="glavnakombinacija">
    <div id="glavniniz"><p id="broj">{{glavnaKombinacija[0]}}</p></div>
    <div id="glavniniz"><p id="broj">{{glavnaKombinacija[1]}}</p></div>
    <div id="glavniniz"><p id="broj">{{glavnaKombinacija[2]}}</p></div>
    <div id="glavniniz"><p id="broj">{{glavnaKombinacija[3]}}</p></div>
    <div id="glavniniz"><p id="broj">{{glavnaKombinacija[4]}}</p></div>
    <div id="glavniniz"><p id="broj">{{glavnaKombinacija[5]}}</p></div>
    <div id="glavniniz"><p id="broj">{{glavnaKombinacija[6]}}</p></div>
    <div id="glavniniz"><p id="broj">{{glavnaKombinacija[7]}}</p></div>
    <div id="tiketkombinacija"></div>
    <div id="sntiketa"><p id="broj">{{idtiketa}}</p></div>
    <div id="tiket"><p id="broj">{{tiketKombinacije[0]}}</p></div>
    <div id="tiket"><p id="broj">{{tiketKombinacije[1]}}</p></div>
    <div id="tiket"><p id="broj">{{tiketKombinacije[2]}}</p></div>
    <div id="tiket"><p id="broj">{{tiketKombinacije[3]}}</p></div>
    <div id="tiket"><p id="broj">{{tiketKombinacije[4]}}</p></div>
    <div id="tiket"><p id="broj">{{tiketKombinacije[5]}}</p></div>
    <div id="pogodci">
    <div id="tiket"><p id="broj">{{pogodci[0]+','+[1]+','+[2]+','+[3]+','+[4]+','+[5]}}</p></div>
    </div>
    </div>
</template>

<script>

export default {
  name: '',
  components: {
 
  },
data: function() {
    return {
      izvuceno: [],             //izvučena kombinacija brojeva
      tiketKombinacije: [],     //generisani ili izabrani tiket
      idtiketa: 0,              //serijski broj tiketa
      tiketi: 0,                //ukupan broj tiketa
      najvisePogodaka: 0,       //navjiše pogodaka - definiše se u poređenju dva niza
      pogodci: [],              //pravi niz od brojeva koji su pogođeni i prikazuje iz na ekranu
      brojPogodaka: 0           //početna vrijednost 
    }
  },

methods: {

Rezultat: function() {
    this.izvuceno.forEach(function(x)
{
  if(this.tiketKombinacija.includes(x))
{
    this.pogodci.push(x);
    ++this.brojPogodaka;
}
})}}}

</script>

<style>

</style>