<template>
  <div id="glavnakombinacija">
    <Header />
    <div id="komb">
            <p id="tiketstat">Kombinacija igre je:</p>
            <p id="tiketstat2"><b>{{testni[0]}}</b> , <b>{{testni[1]}}</b> , <b>{{testni[2]}}</b> , <b>{{testni[3]}}</b> , <b>{{testni[4]}}</b> , <b>{{testni[5]}}</b> , <b>{{testni[6]}}</b> , <b>{{testni[7]}}</b></p>
        </div>
      
      <div class="dobitak" v-bind:key="tiket" v-for="tiket in user">
            <p id="tiketstat">Id tiketa: <b>{{tiket.idtiketa}}</b></p>
            <p id="tiketstat">Kombinacija: <b>{{tiket.kombinacija[0]}},
                            {{tiket.kombinacija[1]}},
                            {{tiket.kombinacija[2]}},
                            {{tiket.kombinacija[3]}},
                            {{tiket.kombinacija[4]}},
                            {{tiket.kombinacija[5]}}</b></p>
            <p id="tiketstat">Broj pogodaka: <b>{{tiket.broj}}</b></p>
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
  props: ['niz','glavna'],
  data(){
    return{
      user: this.niz,
      nesto: this.glavna,
      broj: 0,
      testni: "",
    }
  },
  methods:{
    getRezultat: function(){
      this.testni = this.nesto[0];
      for(let i=0;i<this.user.length;i++)
        {
          
          for(let j=0;j<this.user[i].kombinacija.length;j++)
            {
              if(this.testni.includes(this.user[i].kombinacija[j]))
                {
                  this.user[i].broj++;
                }
            }
        }
    }
  },
created:function(){
  this.getRezultat();
}
}


 
</script>

<style>
.dobitak
{
  background-color: orange;
  border-radius: 8px;
  width: 300px;
  height: 120px;
  align-content: center;
  margin-left: 38%;
}
#tiketstat
{
  color: black;
  padding: 5px;
}
#komb
{
  background-color: rgba(255,165,0, 0.8);
  border-radius: 8px;
  width: 360px;
  height: 90px;
  align-content: center;
  margin-left: 36%;
}
#tiketstat2
{
  color: black;
  font-size: 22px;
}
</style>