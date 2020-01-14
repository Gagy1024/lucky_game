<template>
  <div id="glavnakombinacija">
    <Header />
    <div id="komb">
            <p>Kombinacija igre je:</p>
            
            <p>{{testni}}</p>
            <hr>
        </div>
      
      <div class="dobitak" v-bind:key="tiket" v-for="tiket in user">
            <p>Id tiketa: {{tiket.idtiketa}}</p>
            <p>Kombinacija: {{tiket.kombinacija}}</p>
            <p>Broj pogodaka: {{tiket.broj}}</p>
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

<style scoped>

</style>