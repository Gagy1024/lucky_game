<template >
  <div id="game">
    <div v-if="prekidac">
      <div v-if="prekidac2">
        <Provjera v-on:load="Provjera" v-bind:glavna="glavna" v-bind:niz="korKombinacije"/>
      </div>
      <div v-else>
        <Glkomb v-on:stolic="trollic"/>
      </div>
    </div>
    <div v-else>
      <div id="brojac">
      <Counter v-on:load="Counter" />
      </div>
      <div id="dodaj">
      <Dodjela v-on:add-komb="addKomb" />
      </div>
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
      ispis: {},
      broj: 0,
    }
  },
  created() {
    var self = this;
    setTimeout(function() {
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
    }
}
}
</script>

<style>
  #game{
    text-align: center;
  }
  #brojac{
    display: inline-block;
    margin-left:-37%;
    margin-right:auto;
    margin-top: -120px;
  }

  #dodaj{
    margin-top:40px;
  }
</style>