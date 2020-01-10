<template >
  <div id="game">
    <div v-if="prekidac">
      <div v-if="prekidac2">
        <Provjera v-on:load="Provjera" />
      </div>
      <div v-else>
        <Glkomb />
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
    }
  },
  created() {
    var self = this;
    // Nakon 3 minute (60 sek) pokrenut će se funkcija getRezultat i promjeniti prekidac u false
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
    }
  }
}
</script>

<style>
</style>