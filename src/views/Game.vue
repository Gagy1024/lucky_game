<template >
  <div id="game">
    <div v-if="prekidac">
      <Glkomb />
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

export default {
  name: 'Game',
  components:{
    Dodjela,
    Counter,
    Glkomb,
  },
  data: function() {
    return {
      korKombinacije: [],
      prekidac: false,
    }
  },
  created() {
    var self = this;
    // Nakon 3 minute (180 sek) pokrenut će se funkcija getRezultat i promjeniti prekidac u false
    setTimeout(function() {
      self.prekidac = !self.prekidac;
    }, 60000);
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