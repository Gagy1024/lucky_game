<template>
  <div id="glavnakombinacija">
    <div id="glavniniz"><p id="broj">{{konacniniz[0]}}</p></div>
    <div id="glavniniz"><p id="broj">{{konacniniz[1]}}</p></div>
    <div id="glavniniz"><p id="broj">{{konacniniz[2]}}</p></div>
    <div id="glavniniz"><p id="broj">{{konacniniz[3]}}</p></div>
    <div id="glavniniz"><p id="broj">{{konacniniz[4]}}</p></div>
    <div id="glavniniz"><p id="broj">{{konacniniz[5]}}</p></div>
    <div id="glavniniz"><p id="broj">{{konacniniz[6]}}</p></div>
    <div id="glavniniz"><p id="broj">{{konacniniz[7]}}</p></div>
    <div id="tiketkombinacija"></div>
    <p id="tiket">Kombinacija tiketa:</p>
    <div id="tiket"><p id="broj">{{tiketKombinacije[0]}}</p></div>
    <div id="tiket"><p id="broj">{{tiketKombinacije[1]}}</p></div>
    <div id="tiket"><p id="broj">{{tiketKombinacije[2]}}</p></div>
    <div id="tiket"><p id="broj">{{tiketKombinacije[3]}}</p></div>
    <div id="tiket"><p id="broj">{{tiketKombinacije[4]}}</p></div>
    <div id="tiket"><p id="broj">{{tiketKombinacije[5]}}</p></div>
    <div id="pogodci">
    <p id="pogodjeno">Pogođeni brojevi sa tiketa:</p>
	<div id="pogodci"><p id="broj">{{pogodci[0]}}</p></div>
    <div id="pogodci"><p id="broj">{{pogodci[1]}}</p></div>
    <div id="pogodci"><p id="broj">{{pogodci[2]}}</p></div>
    <div id="pogodci"><p id="broj">{{pogodci[3]}}</p></div>
    <div id="pogodci"><p id="broj">{{pogodci[4]}}</p></div>
    <div id="pogodci"><p id="broj">{{pogodci[5]}}</p></div>
	<div>Broj pogodaka: {{brojPogodaka}}</div>
    </div>
    </div>
</template>

<script>

export default {
  name: 'Provjera',
  components: {
 
 // props: ['komb', 'najvisePogodaka', 'konacniniz']
  },

data: function() {
    return {
	konacniniz: [2,5,8,9,10,25,36,44],          //izvučena kombinacija brojeva
	tiketKombinacije: [
		{
			id:1,
			komb: [1,2,3,4,5,6]
		},
		{
			id:2,
			komb: [7,8,9,10,11,12]
		}
	],
      pogodci: [],              
      brojPogodaka: 0,  
	}},
methods: {

provjera: function() {

this.tiketKombinacije.forEach(function(x){
  for(let i=0;i<x.komb.length;i++)
    {
      if(this.konacniniz.includes(x.komb[i]))
        {
          this.pogodci.push(x.komb[i]);
          this.brojPogodaka++;
        }
    }
});}}}



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
<style>
body {
	font-family: Impact;
  background-image: url('../assets/background.png');
  background-size: 100%;
}

</style>