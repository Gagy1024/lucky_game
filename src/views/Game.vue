<template>
  <div id="game">
    <Dodjela v-on:add-komb="addKomb" />
  </div>
</template>

<script>
import Dodjela from './../components/Gamelayout/Dodjela.vue';

export default {
  name: 'Game',
  components:{
    Dodjela,
  },
  data: function() {
    return {
      korKombinacije: [],
    }
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